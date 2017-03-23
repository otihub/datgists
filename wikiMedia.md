# Getting spatial data from WikiMapia
It is possible to get any data on [Wikimapia.org](www.wikimapia.org) and turn it into a shapefile but it takes a little doing. In this gist we will step through the process of how to download the data and convert it to a shapefile.

## The API
Wikimapia has an [API](www.wikimapia.org/api) for downloading its data. Here is some useful information about the API:
 + Multiple formats for data output including xml, kml, and json.
 + API limit of 100 results per call
 + Can call features in a number of different ways including by location (bounding box), by feature type id, etc.

The API is well documented but if you need help structuring an API call you can fill out the wikimapia api call builder tool built into this [excel tool](https://drive.google.com/file/d/0B_gSDNSQU_UoM2g3RnR3TUlEYjg/view?usp=sharing). Enter the requisite information remembering to select kml as data output. Copy the url api call created into the browser and if any features are captured by the call they should download (up to the limit of 100 imposed by wikimapia).

WikiMapia has its own list of feature ID which you can filter on when selecting features to download. The linked API builder tool has a list of their IDs but I have found it most useful to navigate to what you want to download and read the id number from the feature directly, to do so:
1. Click on the feature
2. Click on the tag under the feature description in the on the left
3. A pane should appear at the top of the screen which says showing category: < the category you chose >. Click on the category name.
4. The id number WikiMapia uses should appear to the right of the feature name when the features description dialog appears.   

## Now to OGR2OGR
Wikimapia exports data as a kml Multi Geometry which does not have native support in QGIS or ArcGIS :(. Never fear we will use the powerful OGR2OGR command line tool to explode the geometries and translate them to a format we can make easier use of, shapefile for example.

In order to translate the Multi Geometry to a shapefile I use the following ogr2ogr command
 ```
ogr2ogr -nlt POLYGON -explodecollections -skipfailures <name of shp> <name of kml>
 ```
