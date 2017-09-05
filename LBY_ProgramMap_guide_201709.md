# Libya Monthly Program Map Instructions

## Intro
The Libya Monthly Program Map is due the second Monday of the Month.  It uses hexbins to depict programming intensity (by `Estimated Amount`) and has an insert map for the "Northwest Costal Cooridtor as it has a high concentration of programming (and population).  Further, a modified version of the disolve script is used to create the hexbin layer.

## Steps

### PostgreSQL Setup
1. Make sure you have PostgreSQL installed on your computer (follow [these instructions](https://gist.github.com/sgnl/609557ebacd3378f3b72) to install via homebrew on a mac). 
2. Login to psql (if you folloed the instructions in the above step, `psql whoami` or `psql another_database`
3. In psql create a database for Libya:`CREATE DATABASE libya`
4. Connect to the Libya database: `\connect libya`
5. Add the PostGIS extention: `CREATE EXTENSIONS POSTGIS`
