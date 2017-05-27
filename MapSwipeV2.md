# MapSwipe 2.0

MapSwipe (mapswipe.org, https://github.com/mapswipe) is a mobile-based, offline geographical imagery tile classification crowdsourcing app that MSF and the Red Cross (along with a few other agencies) use to find inhabited areas for mapping with a feature-creating application. It works somewhat like Tinder, in that users swipe through a large number of images, reacting quickly to what the see (immediately moving on from images lacking identifiable features, and tapping on the tiles within images that do contain features). This makes tracing features more efficient by allowing mappers to spend the bulk of their time on features known to contain something to map, and reduces the likelihood of areas containing features being missed by mappers (who aren't necessarily able or willing to scroll through all available imagery looking for something to map).

MapSwipe could use some improvement purely as an imagery classification application, but it could also be turned into an application to crowdsource the creation of vector features from imagery, massively increasing the number and speed of volunteers digitizing imagery into maps. The general idea is:

- A task creator specifies an Area of Interest and parameters for a mapping task.
  - For example, the region within 40km of Bokoro, Chad, looking for visible roads and all human building structures, with a tile zoom level of 17, road categories including main, secondary, tertiary, and track.  Building default zoom level 1:200, and building categories house, mosque, and other (which is a grab bag of schools, government buildings, and industrial buildings). The task creator also specifies how many users they wish to see each bit of imagery.
- Users who choose to participate in this task download a cache of image tiles from within the Area of Interest to their device (users can modify the size of the cache and whether it uses mobile data, wifi only, or mobile data only when out of images).
- Users then use the current MapSwipe workflow to browse through all of the tiles in their cache, identifying those containing relevant features by tapping on the tiles before swiping to the next batch.  
- After images (tiles) containing features are identified by the current MapSwipe application, a second workflow allows users to view those tiles individually at a higher zoom level. While the MapSwipe classification application displays a number of tiles in one screenful, allowing the user to quickly move on or choose only the tiles containing features, the feature creation application shows each tile filling the entire screen. 
- At this higher zoom level, the user traces along any roads with a finger, creating a polyline along each road.
- These traces are immediately converted to lower-density data structures (dense polylines are not data-efficient ways to represent roads) by approximating them with curves.
- After each trace, a pop-up dialogue appears asking the user to classify the road according to a set of standard criteria provided by the task creator, distinguishing between main roads, secondary roads, tertiary roads, tracks, etc. This popup also allows the user to discard and retry the most recent trace (or to complain about the curve not matching the original trace).
- The user is then prompted to tap on the centre of all buildings. After tapping, the image is zoomed to a predetermined amount (estimated to accomodate most local buildings using 70% of screen area or so by the task's creator, or to the last used building zoom, and adjustable via pinch gesture).
- The user traces around the building with a finger, approximating the shape of the structure's perimeter (rectangular, round, or complex like something made from lego blocks). This creates a dense polyline.
- The perimeter polyline is "snapped" to a regular shape (most buildings, if not round, are made from right angles and parallel walls). A popup gives the user the option to validate, retry, or adjust the resulting perimeter.
  - Bonus feature: In many areas almost all buildings are either round huts or four-cornered rectangles. In these areas, a feature making an automated guess at a perimeter based on pixel color boundaries could save the user the effort of tracing, allowing them to simply validate or correct the guessed perimeter.
- After validating the trace, a second popup can be shown asking the user to classify the building according to the task creator's criteria (metal or straw roof, for example). 
- The vector data (vector curves representing roads, and simplified polylines representing building perimeters), along with their associated data (building types and road classifications) are compressed and uploaded to a server.
- The server then knits the short curve segments of roads into longer lines (possibly averaging the results if multiple users have traced within the same tile). The server also checks algorithmically for mismatching results from different users, flagging these features for attention from a human validator (standard OpenStreetMap practice already includes validation of crowdsourced features).

The results of the crowdsourced mapping can be used to train automated imagery recognition algorithms. I mention this because almost everyone who hears of this project says "Can't you train an AI to do this?" The answer is: "Probably, but where do you plan to get the training data in sub-Saharan Africa? And even if your AI is fantastically good at identifying white houses in light-green clearings throughout the dark-green Congolese forest, how will it perform on round brown huts on a brown background full of round brown trees and round brown rocks in the Sahel?" I suspect that there are more people working on automated imagery classification than really effective large-scale crowdsourcing, and most of those projects will be very glad indeed to use our data.

### Resources and skills needed
- Android development
  - MapSwipe was developed using React Native, so some knowledge of that is probably useful
- GIS back end development
  - The GDAL library is incredibly useful for this
  - Knowledge of OSM XML, PostGIS databases, and GIS data types in general useful
  - Knowing how tile servers work is helpful
- Integration with OSM and HOT Tasking Manager
  - This is how the Humanitarian OpenStreetMap Team currently tasks areas: https://github.com/hotosm/osm-tasking-manager2
  - Importing the crowdsourced data into OSM is non-trivial: http://wiki.openstreetmap.org/wiki/Import/Guidelines
- Design
  - Stuff like MapSwipe works because it feels like a game. Not to say frivolous, or loaded with smarmy manipulative incentives, but responsive and fun to use. That's not just a coder's job; quality visual and UX design matters a great deal.
- Efficient server-client communication
   - This application can generate quite a lot of data transfer, which can become unwieldy for both the client (and the user's data plan) and the server. Optimizing data transfer and sync is a big help.

<hr>

# Descriptions of functionality (for mock-ups)

- Tracing a road: the user is moving a finger along a road, creating a visible trace along that road. 
  - Upon finishing the trace, a popup appears asking the user to classify the road according to some schema, for example 1) primary road, 2) secondary road, 3) track (these might include example images showing what these choices look like)
  - Issue: what if there's a road oriented in such a way that tracing it duplicates the movement of swiping to the next tile?
    - Mitigation: perhaps the "swipe to the next tile" gesture is faster. Less attractively, perhaps the tracing gesture begins with a tap to differentiate it from a swipe (similar to the common "tap-and-move" gesture for dragging items).

- Tapping on a building to zoom in on it: buildings are usually too small to trace comfortably with the tile at full size. In fact, we probably want the building to basically fill 70% of the screen, even though this will pixillate the hell out of it; it allows the user to comfortably trace around the building. A second tap should un-zoom, and while in zoomed state a pinch gesture should allow adjustment of the zoom (the default zoom should be the previous zoom the user was at prior to tapping out)

- Tracing a rough line around a building: the user zooms around the building with a finger, creating a rough outline. Once the trace is completed and the finger lifts, the trace, if closed (the endpoint is within a few pixels of the beginning point), it automatically jumps to the next step (the snap).

- Snapping a rough outline to a simplified and symmetrical one: if the trace is nearly circular (like a lot of African huts) the rough outline will snap to a circle (actually a polygon with 12+ vertices to look nearly round).  If it's not circular, it snaps to an outline composed of right angles (most buildings do not have parallelogram shapes). The snap is accompanied by buttons (outside of the outline, or at least not overlapping the perimeter) allowing the user to 1) accept or 2) discard the snapped result, or 3) to keep the hand-trace unsnapped (in the occasional event of buildings that don't correspond to either a round or rectilinear shape).  

### Less important, but still useful:

- Swiping to a new tile: the fundamental underlying UX gesture of MapSwipe is swiping to the next thing. This maintains consistency for users coming from the classification activity. Right-swipe=next tile.  Tiles are shown filling the entire screen, unlike in the classification app where there are six tiles per screenful.  A cool mockup would be mid-swipe.

## A few tiles to play with:

Chad zoom 18 huts:

http://t0.tiles.virtualearth.net/tiles/a122213321100212200.jpeg?g=854&mkt=en-US&token=AopsdXjtTu-IwNoCTiZBtgRJ1g7yPkzAi65nXplc-eLJwZHYlAIf2yuSY_Kjg3Wn

Chad zoom 19 huts:

http://t0.tiles.virtualearth.net/tiles/a1222133211002122001.jpeg?g=854&mkt=en-US&token=AopsdXjtTu-IwNoCTiZBtgRJ1g7yPkzAi65nXplc-eLJwZHYlAIf2yuSY_Kjg3Wn

http://t0.tiles.virtualearth.net/tiles/a1222133211002122012.jpeg?g=854&mkt=en-US&token=AopsdXjtTu-IwNoCTiZBtgRJ1g7yPkzAi65nXplc-eLJwZHYlAIf2yuSY_Kjg3Wn

Congo zoom 18 houses:

http://t0.tiles.virtualearth.net/tiles/a122323223200031101.jpeg?g=854&mkt=en-US&token=AopsdXjtTu-IwNoCTiZBtgRJ1g7yPkzAi65nXplc-eLJwZHYlAIf2yuSY_Kjg3Wn

Congo zoom 18 houses and roads:

http://t0.tiles.virtualearth.net/tiles/a122323223200031103.jpeg?g=854&mkt=en-US&token=AopsdXjtTu-IwNoCTiZBtgRJ1g7yPkzAi65nXplc-eLJwZHYlAIf2yuSY_Kjg3Wn

Congo zoom 19 houses:

http://t0.tiles.virtualearth.net/tiles/a1223232232000311013.jpeg?g=854&mkt=en-US&token=AopsdXjtTu-IwNoCTiZBtgRJ1g7yPkzAi65nXplc-eLJwZHYlAIf2yuSY_Kjg3Wn

http://t0.tiles.virtualearth.net/tiles/a1223232232000311012.jpeg?g=854&mkt=en-US&token=AopsdXjtTu-IwNoCTiZBtgRJ1g7yPkzAi65nXplc-eLJwZHYlAIf2yuSY_Kjg3Wn
