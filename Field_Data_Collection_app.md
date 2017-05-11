## Unnamed GIS Field Data Collection Mobile App

Update: looks like someone has had a good crack at this:
http://www.opengis.ch/ An app called QField, though it looks like parts of it are broken

Geographical Information Systems have become incredibly accessible. QGIS (qgis.org) is an astoundingly capable free software GIS platform, allowing anyone with the requisite knowledge, skill, and a low-end laptop to produce high-quality maps without spending a penny on software (though I strongly encourage anyone who uses it professionally, for pay, to donate money to the project; I do so myself).

More sophisticated users with command line abilites can use spectacularly powerful tools like PostGIS, R, and GDAL (anyone thinking of sneering, have a look at by buddy Stephen Mather's blog: https://smathermather.com/category/analysis/; if you think free GIS software is for amateurs I'd like to to see you tangle with Steve).

High-quality, high-resolution maps built from locally sourced field data are potential game-changers for a number of fields of endeavor in Africa, notably property delineation (a huge problem for poor people), environmental monitoring, and construction. My own field of primary interest, health care, doesn't typically require very high spatial accuracy (a few meters is usually more than fine), but several related fields such as water and sanitation are well-served by highly accurate GIS data (see related challenge [Differential correction for mobile device GPS units](https://github.com/ivangayton/challenges/#)

The full power of GIS is available when you have a field data collection application and hardware and a GIS software platform. The latter requirement has been knocked out of the park, but the current options for field data collection remainare limited. Dedicated hardware is expensive; it costs several thousand dollars for a high-accuracy commercial GPS device. However, the GPS units in ordinary Android phones can be surprisingly accurate, and there's room for improvement with the above related challenge.

The main gap: there simply isn't a high-quality free software mobile data collection application out there. This drives people back into the arms of the commercial GIS vendors, whose free-as-in-beer (or perhaps better described as bait-and-switch) offerings require users to buy into their walled gardens of proprietary software, making decent GIS data collection difficult for people in low-income countries to access (note: while I am indeed an ideological supporter of free software, so you can save yourself the time of pointing out that bias, in this case what I'm talking about is purely practical: the inaccessibility of proprietary software to African citizens who could otherwise be full partners in the mapping of their own continent).

What does a full-featured mobile GIS data collection application need to complete the free software GIS ecosystem?

- The ability to record points, polylines, and polygons in the field, offline, from a GPS receiver.
  - A friendly GUI allowing non-experts to understand and accomplish this.
  - Tools to easily choose between creating a feature at the exact position of the GPS receiver itself, or offsetting (i.e. creating a line 10 meters to the east of the road one is walking along, or tagging the centre of a building one is standing in front of).
- The ability to communicate GPS information in the NMEA standard http://www.gpsinformation.org/dale/nmea.htm
    - This should allow the application to use an external GPS receiver when higher spatial accuracy than the onboard GPS can provide is needed. 
  - As an added bonus, the ability to store GPS information in the RINEX format to allow for differential correction https://en.wikipedia.org/wiki/RINEX https://igscb.jpl.nasa.gov/igscb/data/format/rinex303.pdf
- The ability to display maps from a desktop GIS system with the appropriate formatting, including locally rendering all raster and vector data on the fly.
  - For example, taking a QGIS project file (which is xml) along with its associated data files (or subset thereof corresponding to the working area and GIS layers), importing them to the mobile device, and rendering the map locally such that the user can zoom just as they can in a desktop GIS, with lines, labels, and icons scaling smoothly.
  - When recording new features, for those to immediately display on the map with the appropriate styling.
  - When recording new features, for a popup dialogue to prompt for the appropriate associated data. 
    - For example, if you're mapping fire hydrants, and your main map shows a little fire hydrant icon for the already-mapped ones, when you add a new hydrant you don't want to just select "point" and fill out the description "Hydrant #324," and have the hydrant display as a dot until you get back to the office and integrate it into the Fire_Hydrant layer. You want to select "Fire Hydrant," have the popup dialogue immediately ask for "Hydrant number" (and provide you with a number pad rather than a keyboard), along with whatver other information you want related to that hydrant (condition, color, age, type, whatever). Then you want it to immediately display as a fire hydrant icon just like the others (or optionally with a different color to indicate that it's a new data point from the current session).
  - Reading and writing to standard GIS vector data formats (ESRI Shapefile, Spatialite, KML, OSM XML, etc).
  - Reading and displaying (not writing or modifying) standard GIS raster data formats (GeoTIFF, various image formats with Ground Control Points, World Files, etc).
  - Loading, displaying, and caching imagery tiles from tile servers.
- A GUI-based utility for exporting desktop GIS projects and data to the mobile device smoothly, specifically omitting layers and areas not needed for the planned data collection mission (this avoids bogging down the mobile device with too much information).
- The ability to accomodate plug-ins so that people with specific data collection needs can create their own utilities.
  - For example, surveyors often want to record a point for a feature they can't easily reach. Even though they have a GPS receiver, they tend to carry an accurate compass! Therefore, it is possible to take two or more compass readings from known points, and have the correct point calculated and displayed automatically in the software. This kind of utility can be included in the main software package, but then the developer has to think of everything. It's even more powerful if the software is built in such a way that people can add this type of functionality as a plug-in. Recommendation: build that particular feature (points from triangulated compass bearings) as a plug-in, forcing yourself to build the software extensibly.


### Resources and skills needed:
- Android development
- GIS data formats
- projections
- Knowledge of QGIS, ability to port display code 
- Probably good idea to know OpenDataKit as well, as it's got a brilliant set of functions for collecting type-specific data with appropriate widgets

