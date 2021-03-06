# Airport Map of U.S. on Mercator Projection

For this project, a choropleth map of the United States is displayed based on how many airports are located within each state. The locations of airports in each state are also displayed. Upon clicking on each location, the name of that airport is then displayed in a popup message. Each airport location is marked by a paper airplane icon.

There were several key functions in the making of this map. The map, zoom level, and area of view are defined in "L.map". "L.geojson.ajax" allowed the placement of GeoJSON data onto the map, with "pointToLayer" defining subgroups of the data (airport locations) and "onEachFeature" displays a popup with info defined in the function. Color scales are declared with the function "chroma.scale", which are then added to states within the function "fillColor" of "style". "setColor" assigns states to a color on the predefined color scale based on a determined ID number. The function "legend.onAdd" set up a map legend, in which each element can be defined line by line along with a short description for each element. In addition to these functions, which I used in a previous lab in a web mapping course that can be found here: https://github.com/kkstuvstad/usairportmap, I used several new functions. The function "latlngGraticule" allowed the creation of a graticule or grid where I could set zoom intervals that would go hand in hand with the spacing of the latitude and longitude intervals. The function "addLabel" made it possible to add names to label each state and to adjust its size, in which this function utilized the Label Gun library. The function "L.Proj.CRS" set the projection of the map to the projection of my choice with its name and string of code that would be understood using the "proj" extension. 

For color choices, the choropleth map of states was set from yellow for states with few airports and dark red for states with multiple airports. Purple was assigned to airports that had a control tower while dark green was assigned to airports that did not have a control tower. I set multiple zoom intervals for the graticule. Specifically, the interval is 2 degrees for zoom level 1, 1 degree for zoom levels 2 and 3, 0.5 degrees for levels 4 and 5, and 0.25 for levels 6 and 7. Green was applied to the graticule lines while purple was assgined to the graticule font as to keep consistent with the colors used for the airport locations. 

For the projection, I chose the WGS 1984 Web Mercator projection. The WGS 1984 Web Mercator projection displays all of the earth on a flat surface. Areas near the Equator are the most accurate in terms of shape, but is increasingly distorted the closer the area is to one of the poles. However, this projection is good at displaying location data once it is reprojected (ESRI, 2010). While this projection has no impact on the color that is being displayed for each state, this does maintain accuracy for the location of the airport as opposed to altering their true locations.

## Sources:
* Project based off of Lab 2 of GEOG 4/572 by Bo Zhao of Oregon State University
* ESRI, "Web Mercator", 2010, https://www.esri.com/events/seminars/bettermaps/~/media/files/pdfs/events/seminars/bettermaps/materials/pdfs/webmercatorsmnrbrochure.pdf
* Link to projection used: https://spatialreference.org/ref/sr-org/45/
* Airport Data: Data.gov, https://catalog.data.gov/dataset/usgs-small-scale-dataset-airports-of-the-united-states-201207-shapefile
* US States Data: Mike Bostock: https://bost.ocks.org/mike/, D3: https://d3js.org/
* Font Awesome Icon: https://fontawesome.com/icons/paper-plane?style=solid
#### Libraries Used (can be located in index.html code file):
* Leaflet CSS: https://unpkg.com/leaflet@1.4.0/dist/leaflet.css
* Font Awesome, version 4.7.0: https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.css
* Ubuntu Font: https://fonts.googleapis.com/css?family=Ubuntu
* Rbush.min.js: https://unpkg.com/rbush@2.0.1/rbush.min.js
* Label Gun: https://unpkg.com/labelgun@6.0.0/lib/labelgun.min.js
* Leaflet JS: https://unpkg.com/leaflet@1.4.0/dist/leaflet.js
* Leaflet Ajax: https://cdnjs.cloudflare.com/ajax/libs/leaflet-ajax/2.1.0/leaflet.ajax.min.js
* jQuery: https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js
* Chroma.js: https://cdnjs.cloudflare.com/ajax/libs/chroma-js/1.3.4/chroma.min.js
* Proj4 JS: https://cdnjs.cloudflare.com/ajax/libs/proj4js/2.4.4/proj4.js
* Proj4 Leaflet: https://cdnjs.cloudflare.com/ajax/libs/proj4leaflet/1.0.2/proj4leaflet.min.js
* Leaflet Graticule: https://cloudybay.github.io/leaflet.latlng-graticule/leaflet.latlng-graticule.js
