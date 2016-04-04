#Syria/Iraq Areas of Influence Technical Documentation

For local users: [link to gist on Github](https://gist.github.com/cwlawlis802/1fbfebf4d177ff4e49a9/edit).

#Syria

*Note:* Original documentation `Syria_Areas of Control Map_Geoprocessing Technical Steps` available on Q: `Q:\GIU_Documents\OTI\Guidance for OTI GIS Analysts - Map Procedures\Syria`

This is technical guidance on producing the aggregate, smoothed shapefile depicting areas of influence in Syria. We implement a series of geoprocessing functionalities within ArcGIS and combine basic spatial data with Landscan gridded population to create a cartographically sound data set.

##Key
- `AOI` refers to **Areas of Influence**
- `OTIA` refers to **OTI Anywhere**
- `Q:` refers to the **Q: Drive**
- `YYYY` refers to the **year** e.g. 2015
- `MM` refers to the **month** e.g. 03 for March
- `DD` refers to the **day** e.g. 10 for the 10th

##Pull down the data

- Pull down OTI AOI data from [OTIA](https://otianywhere.net/folder/database-3?gids[]=15664&pnid=0) to Q: `Q:\GIU_Workspace\Country\Syria\Data_Sets\Situational Data\Areas of Control\OTI\YYYYMMDD`    

- Pull down OCHA AOI data to Q: `Q:\GIU_Workspace\Country\Syria\Data_Sets\Situational Data\Areas of Control\OCHA\YYYYMMDD`

##Convert OTI data to spatial format

###Sub Region

- Join `Sub_Regions_MM_DD_YYYY` tab to Ministry of Local Administration's `Sub_Regions.shp` in `Q:\GIU_Workspace\Country\Syria\Data_Sets\Base Data\Boundaries\Ministry of Local Administration` on `Nahia_Code` field.

- Export to current OTI AOI directory (`Q:\GIU_Workspace\Country\Syria\Data_Sets\Situational Data\Areas of Control\OTI\YYYYMMDD`) as `Syria_AOI_SubDistrict_YYYYMMDD.shp` using date of data

###Neighborhood

- Copy previous Aleppo neighborhood control shapefile `Syria_AOI_Aleppo_YYYYMMDD.shp` into current OTI AOI directory (`Q:\GIU_Workspace\Country\Syria\Data_Sets\Situational Data\Areas of Control\OTI\YYYYMMDD`) and remove `Control_St` field

- Join `Aleppo_Neighborhoods_MM_DD_YYYY` tab to `Syria_AOI_Aleppo_YYYYMMDD.shp` on `SRCode` field

- Export to current OTI AOI directory as `Syria_AOI_Aleppo_YYYYMMDD.shp` using date of data

##Convert polygons to raster

-	Use `Polygon to Raster` tool (`Conversion Tools` > `To Raster`) to convert OTI subdistrict shapefile:
  - Set `Value field` to `Control_St`
  - Set path to current OTI AOI directory and save as `districts_ras`
  - Set `Cell assignment type` to `MAXIMUM_AREA`
  - Keep `Priority field` at `NONE`
  - Set `Cellsize` to `500`

**OTI AOI raster data classification will be as follows:**

1. Regime
2. Contested
3. Anti-ISIS (Moderate Opposition)
4. ISIS
5. Kurdish
6. JAN

-	Use `Polygon to Raster` tool (`Conversion Tools` > `To Raster`) to convert OCHA shapefile:
  - Set `Value field` to `Actor_Type`
  - Set path to current OCHA AOI directory and save as `ocha_ras`
  - Set `Cell assignment type` to `MAXIMUM_AREA`
  - Keep `Priority field` at `NONE`
  - Set `Cellsize` to `500`

**OCHA AOI raster data classification will be as follows:**

1. Armed opposition groups and ANF  
2. Contested Areas  
3. Government (SAA)  
4. ISIS-affiliated groups  
5. Kurdish Forces

##Reclassify OTI raster to match OCHA

**Note: Must be done before merging both rasters to ensure correct attribute transfer**

- Use `Reclassify` tool (`Spatial Analyst Tools` > `Reclass`) to reclassify OTI raster so attribute values for control match OCHA:
  - Set `Input raster` to `districts_ras` 
  - Set `Reclass Field` to `VALUE`
  - Set `Reclassification` as follows (switching `Regime` and `Anti-ISIS (Moderate Opposition)` to match OCHA, with `JAN` remaining):

    | Old Values  | New Values |
    | ----------- | ---------- |
    | 1 | 3 |
    | 2 | 2 |
    | 3 | 1 |
    | 4 | 4 |
    | 5 | 5 |
    | 6 | 6 |

  -	Save to same directory and name `ras_reclass`
  -	Check output raster to ensure attribute table values match the OCHA raster

##Merge rasters

- Use `Mosaic to New Raster` tool (`Data Management Tools` > `Raster` > `Raster Dataset`) to merge OTI and OCHA rasters:
  - Add the rasters to the `Input Rasters` list, making sure the OTI `ras_reclass` is listed first
  - Set the `Output Location` to the current OCHA directory `Q:\GIU_Workspace\Country\Syria\Data_Sets\Situational Data\Areas of Control\OCHA\YYYYMM`
  - Name the file `control_merge.tif` (make sure to include `.tif` extension)
  - Set `Spatial Reference for Raster` to `WGS_1984_UTM_Zone_37N` 
  - Keep the `Pixel Type` unchanged
  - Set `Cellsize` to `500`
  - Keep `Number of Bands` at `1`
  - Set `Mosaic Operator` to `FIRST`
  - Set `Mosaic Colormap Mode` to `REJECT`

##Remove sparsely populated areas

- Use the `Raster Calculator` tool (`Spatial Analyst` > `Map Algebra`) to remove sparsely populated areas by multiplying the merged control raster by the modified Landscan raster layer:
  - Multiply the `control_merge` raster with the population layer `populated_sy`in `Q:\GIU_Workspace\Country\Syria\Data_Sets\Base Data\Human Geography Data`
  - *Note: this is the population layer derived from Landscan 2011. Each sq/km with less than 10 people was removed and, for these calculation purposes, each sq/km was given a value of 1 to maintain the same values for the output areas of control raster*)
  - Save output raster layer as `control_pop` in same OCHA directory

##Add "Control" field to output raster

- Add field to `control_pop` named `Control` type `Text` to give each output value its corresponding control group
- Begin an editing session and enter the corresponding control group per value in each table row:
  
    | VALUE  | COUNT | Control | 
    | ------ |------ | ------- |
    | 1 | X | Moderate Opposition |
    | 2 | X | Contested |
    | 3 | X | Regime |
    | 4 | X | ISIS |
    | 5 | X | Kurdish |
    | 6 | X | JAN |

##Convert raster back to vector for final smooth output

- Use the `Raster to Polygon` tool (`Conversion Tools` > `From Raster`) to convert back to vector:
  - Set `Field` to "Control"
  - Save to same folder
  - Name `aoi_YYYYMMDD.shp`
  - Un-check the box `Simplify polygons` to keep the pixelated shape

- Use the `Smooth Polygon` tool (`Cartography Tools`> `Generalization`) to create the final smoothed polygon for use on the map:
  - Name `aoi_YYYYMMDD_smooth.shp`
  - Set `Smoothing Algorithm` to `PAEK`
  - Set `Smoothing Tolerance` to `5 Miles`.
  - Un-check the box `Preserve endpoint for rings`

##Import into ArcGIS, Export to Illustrator

- Import the final output `aoi_YYYYMMDD_smooth.shp` file and `Syria_AOI_Aleppo_YYYYMMDD.shp` Aleppo neighborhoods file into the `OTI_Syria_AOI.mxd` in `Q:\GIU_Workspace\Country\Syria\GIS_Projects` and import symbology from existing layers

- *Note:* The Damascus neighborhood data is outdated at this point and needs to be revisited. The current data is from NGA/CENTCOM: `Damascus_Suburbs_Neighborhoods_CENTCOM_Control_20140420.shp` in `Q:\GIU_Workspace\Country\Syria\Data_Sets\Situational Data\Areas of Control\NGA\20140412\Processed`

- Export to Illustrator and style the finished product

##Data Sharing

Email maps (both Syria and Syria/Iraq) to the following upon completion. **[Data]** indicates sharing data too:
- OTI Syria DC listserv (dcha.otisyriadcteammaillist@usaid.gov)
- Chris Williams @ DCHA Syria Task Force (cwilliams@usaid.gov)
- Hila Hanif @ OTI via DoD (hhanif@usaid.gov)
- Chris Koltalo @ OFDA GIU (mechr_gio@ofda.gov and ckoltalo@ofda.gov) **[Data]**
- Rachel Starner @ USAID Mission in Baghdad (rstarner@usaid.gov) **[Data]**
- State HIU: **[Data]**
  - Benson Wilder (wilderbf@state.gov)
  - Erika Nunez (NunezEK@state.gov)
  - Tom Gertin (GertinTJ@state.gov)
  - Dennis King (KingDJ2@state.gov)
  - Erin Sawyer (SawyerEA@state.gov)
  - Christine Fellenz (FellenzCL@state.gov)
  - Stephanie Bartlett (BartlettSH@state.gov)

Listed here for easy copy paste into email:

`dcha.otisyriadcteammaillist@usaid.gov, cwilliams@usaid.gov, hhanif@usaid.gov, mechr_gio@ofda.gov, rstarner@usaid.gov, wilderbf@state.gov, NunezEK@state.gov, GertinTJ@state.gov, KingDJ2@state.gov, SawyerEA@state.gov, FellenzCL@state.gov, BartlettSH@state.gov`

Data currently shared with the following. Use [this doc](https://docs.google.com/a/usaid.gov/document/d/1Fo_pXdkA3N4eXwHCgK6AmEaLGhHSMPV859nDPpylF5w/edit) to track data distribution over time.

- USAID
  - ME Bureau
  - OFDA
  - CMC
  - Iraq Mission
- State HIU
- CENTCOM
- Open Source Center
- NGA (National Geospatial-Intelligence Agency)
- MCIA (Marine Corps Intelligence Agency) 
  - Human Geography Branch Head in Geospatial Intelligence Division
Congressional Research Service
  - Foreign Affairs, Defense, and Trade Division
