#Georeference a JPEG & Create a New Shapefile using ArcMap

OTI Country: Somalia
Written by Eva Adler
___________________________________________________________________________________________________
##Intro

The purpose of this gist is to illustrate the use of PDF and JPEG images when available geospatial data is limited, like in the case of the Somalia program. In Part 1, you will learn how to georeference a PDF or JPGEG image in QGIS by aligning it with the same projectiion used in ArcMap. In Part 2, you will learn how to digitize this information and create a shapefile for your own use.

This process was especially helpful for illustrating **Areas of Control** in Somalia when there's little to no information on who controls specific geographic areas.
___________________________________________________________________________________________________

##PART I: Georeference an Image in QGIS

###1. Convert the PDF image into a JPEG image if not already done

Open Photoshop 

File -> Open the PDF file of choice

File -> ‘Save As’ 

Select ‘JPEG’ format from the drop down menu and choose ‘12’ or ‘Highest Quality’

Select the ‘Save’ button.

###2. Georeference the JPEG in QGIS

Open QGIS Desktop 

Ensure the Georeferencer plugin is installed by navigating to ‘Plugins’ -> ‘Manage and Install Plugins’ and search for the ‘Georeferencer GDAL plugin’ in the search bar

Select the ‘Georeferencer GDAL’ box to ensure it has a black ‘x’

Select the ‘Close’ button

Navigate to the ‘Raster’ tab at the top of the QGIS screen

Select ‘Raster’ -> ‘Georeferencer’ -> ‘Georeferencer’ with a plaid icon. Now the georeferencer window will open

Select File -> ‘Open raster’ and navigate to the JPG image. 

A screen will pop up titled, ‘Coordinate Reference System Selector’ and select WGS 1984 coordinate system unless recommended otherwise. Select ‘OK’. Your image will now be loaded into the Georeferencer window

###3. Use Google Maps or ESRI ArcMap to retrieve coordinate points for georeferencing in QGIS

 _**Google Map**_
  
  Use your mouse to click once so a grey location icon pops up with the lat (Y/North), long (X/East) coordinates
  Note: Google Maps uses the (X/East, Y/North) order
  In the next step, input the coordinates into QGIS in this order

  _**ESRI ArcMap**_
  
  Use the blue ‘i’ information tool to click once on a given point of reference and an informational window will pop up with lat, long   coordinates listed next to ‘Location’
  Note: ArcMap uses the (X/East, Y/North) order
  In the next step, input the coordinates into QGIS in this order

###4. Georeference in QGIS

  In QGIS, select the ‘Add a Point’ yellow and grey geometric icon
  
  A window titled, ‘Enter map coordinates’ will pop up. Input coordinates for that particular place as gathered from Google Maps or ESRI ArcMap
  
  Continue this process until you have 4-5 points at minimum. The more reference points available the more accurate the georeferenced image will be
  
  Once you have your points set, navigate to ‘Settings’ -> ‘Transformation settings’ at the top of the georeference window
  
  In the ‘Transformation Settings dialogue box, select the new location for your output raster
  Select ‘OK’
  
  Back in the georeference window, navigate to ‘File’ -> ‘Start georeferencing’

_Once completed, the newly georeferencedfiles into QGIS. If it matches up, congrats! You’ve completed your georeferencing mission. Now onwards to **Part II: Create a New Shapefile**_

______________________________________________________________________________________________________________
##PART II: Create a New Shapefile from the Georeferenced Image in ESRI ArcMap

###1. Create a New Shapefile in ArcCatalog

  In ArcMap select the ‘Catalog’ yellow icon in the menu bar at the top of the screen and navigate to the folder location where you would like this new shapefile stored
  
  Right click on the folder and select ‘New -> ‘Shapefile’
  
  A pop up window appears and type in a name for the shapefile and select ‘Polygon’ from the drop-down menu. Select the ‘Edit’ button at the bottom right to select the WGS 1984 coordinate system or the same one used to georeference the jpg in QGIS.
  
  Select ‘Ok’ and it should now appear in the folder in the ArcCatalog window.

###2. Add Topology Rules to the New Shapefile

  Select topology rules before editing and adding polygon shapes
  Select ‘Must Not Overlap’ and ‘Must Not Have Gaps’
  
###3. Edit the New Shapefile in ArcMap

  Navigate to the ArcMap screen and the new shapefile should be loaded into ArcMap. Now add the georeferenced jpg image by selecting the ‘Add Data’ icon at the top of the screen
  
  Right click the new shapefile and select ‘Edit Features’ then select ‘Start Editing’
  
  Use the ‘Create Features’ window to the right of the ArcMap screen to create new polygon features that resemble the Areas of Control data shown in the georeferenced jpg image
  
  ‘Save’ edits often
  
  Once all areas have been drawn or digitized, select ‘Save Edits’ and then ‘Stop Editing’ in the Editor Toolbar
  Right click the shapefile and select ‘Open Attribute Table’
  
  In the pop up window click the drop-down menu in the upper left and select ‘Add Field’. During this step be sure you’re not highlighting or selecting anything by location on the map
  
  Name your new field ‘Areas_Cntrl’ (or other relevant title) and select ‘Text’ under type so you're able to areas of control information
  
  Now select ‘Start Editing’ in the Editor Toolbar and add militia names under the newly created field in the attribute table

