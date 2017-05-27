# QuantumPad

Software intended to facilitate professional-quality field geographical data collection on consumer mobile devices (phones or tablets), with an emphasis on environments without connectivity.

## Requirements:

- Collect geographical primitives (points, lines, and polygons) in native GIS formats, including ESRI shapefiles, Spatialite, GeoJSON, KML, .osm xml, obf/pbf, as well as good 'ol GPX.  

- Collect vertices using either the built-in GPS reciever on the mobile device, an external (higher-precision) GPS reciever, including one implementing differential correction (real-time or post-corrected), or points chosen by the user by pressing on the screen.  Save metadata for later differential correction.

- Display geographical data from native GIS files according to styles, at a minimum including QGIS styles and OSM styles.  Perform basic modification of these styles (for example changing line thicknesses and colors).

- Display labels from chosen data columns, and perform basic modification of the label styling (font size and color, placement along or above lines, etc). 

- Collect user-defined features such as roads, buildings, parks, and fire hydrants.  This requires collecting primitives (points, lines, polygons) with defined styling, and, most critically, attributes in defined schema appropriate to the features.

- Display pre-loaded georeferenced images and/or tiles.

- Display underlay imagery tiles from remote servers such as Google Earth, Bing Maps, OpenStreetMap, etc.  Where legally possible,  implement pre-caching of such tiles before venturing out of connected areas.  Where caching is not currently legally possible, architecture allows caching at the sole discretion of the user without actively implementing such features; this is to avoid restricting users in places where such caching is legally permitted or in the future when it may no longer be prohibited.

- Implement map styles as imported from QGIS or tile renderers (xml/css).  Users can create and style maps in QGIS or a tile renderer (Stamen, Mapbox, whatever), and export a project folder containing all of the relevant data files and styling to QuantumPad, where the styling remains nearly identical.  Users can select particular datasets to add to, and those datasets will continue to display in the chosen style during collection.  For example, when a user chooses to extend a road, they select the road layer, choose which of the sub-types (e.g. primary or secondary road, which display differently), and begin creating a trace.  The ongoing trace displays identically to the pre-existing roads of the same subtype, which are in turn nearly identical to the style of the original map prepared by the user on their desktop.  Alternately, the user can choose for the ongoing trace to display as "selected" (highlighted or otherwise differentiated from the pre-existing roads).

- Create attributes for collected features using forms such as Xforms as implemented in OpenDataKit.  Edit attributes of pre-existing features using a table view and/or pre-populated form view.  When completing a feature, the user is presnted with a form to input the fields relevant to that feature, which were created and/or selected by the user in the desktop prior to exporting to QuantumPad.

## Outputs

