# Libya Monthly Program Map Instructions

## Intro
The Libya Monthly Program Map is due the second Monday of the Month.  It uses hexbins to depict programming intensity (by `Estimated Amount`) and has an insert map for the _Northwest Costal Corridor_ as it has a high concentration of programming (and population).  Further, a modified version of the disolve script is used to create the hexbin layer.

## Steps

### PostgreSQL Setup
The script uses the relational database PostgreSQL (psql) with it's geospatial extension, PostGIS to perform the dissolve commands and to export the data as ashapefile.  Note that you only have to do this once!

1. Make sure you have psql installed on your computer (if you don't, follow [these instructions](https://gist.github.com/sgnl/609557ebacd3378f3b72) {:target="_blank"} to install via homebrew on a mac). 
2. Login to psql (if you folloed the instructions in the above step, `psql whoami` or `psql another_database`
3. In psql create a database for Libya:`CREATE DATABASE libya`
4. Connect to the Libya database: `\connect libya`
5. Add the PostGIS extention: `CREATE EXTENSIONS POSTGIS`

### Adding Hexbins
To add activity data to the hexbins, we first need to load a blank shapefile.  Think about how you would do this in Arc or QGIS.  First you would create your hexbin layer, and then with the activity points, you would perform a spatial join and count/sum for each activities in one of the hexbin grids.  The sql commands perform the same actions.  Luckily you only have to load the blank hexbin shapefile once!

1.  Luckily Rory already made a blank hexbin shapefile for you...make sure to thank him with a high-five.  You can find the blank hexbin shapefile at the following path: `/Volumes/GIU/GIU_Workspace/Country/Libya/Data_Sets/OTI Data/Activities/_emptyHexbins/emptyHexbins.shp`
2.  To load the shapefile into our libya database, we need to run the following command in terminal (not psql): `shp2pgsql -I -s 4326 path/to/emptyhexbin.shp emptyhexbins | psql -d libya`  Make sure you update the path in the command to the path of where the empty shapefile is stored. 

### Update the Dissolve Script
The next step is to update the variables and paths in the dissolve script itself.  A template script can be found here `test` make sure to make a copy of it and update your own script.
 1. 


Now that we have: psql, the libya database, and our hexbins loaded 
