#Syria/Iraq Areas of Influence Technical Documentation

For local users: [link to gist on Github](https://gist.github.com/cwlawlis802/1fbfebf4d177ff4e49a9/edit).

#Syria

*Note:* This documentation (and the product) has changed dramatically since we started utilizing the AOC data produced by our implementing partner. Original documentation `Syria_Areas of Control Map_Geoprocessing Technical Steps` available on Q: `Q:\GIU_Documents\OTI\Guidance for OTI GIS Analysts - Map Procedures\Syria`

This is technical guidance on producing shapefiles depicting areas of influence in Syria. There are a few steps necessary to prepare the data for sharing including aggregation and appending of metadata


##Clean Data

- Receive data from partner, load in GIS
- Data comes converted from KML format so delete all the unecessary fields Except "snippet" which contains control data using the **table manager** tool or equivilent in ArcGIS.
- Rename `snippet` column to `Control` 
- Save data and close out of QGIS
- Bring into ArcGIS and run the `Repair Geometry` tool to get rid of self intersections.
- Run the `Dissolve:Data Management` tool to dissolve features by Control Type.

##Apply MetaData
- Delete the metadata file created by default by ArcGIS (it should be the one with the .xml file extension.
- Exit out of ArcGIS and Navigate to the AOC dataset in ArcCatalog. 
- View description tab and click Import (ensure you are importing from ArcGIS standard), navigating to the latest AOC data that has "Share" in the file name to select its metadata, import. 
- A few things will have to be edited in the metadata to bring it up to date. Mainly the dates. 
  - In Metadata:Details Change the Date Stamp to the Current Date 
  - In Resource:Distribution Change Distributor > Available Dates to Current Date 
  - In Resource:Fields Change Control/Beginning and Ending Date of Values to reflect the datas shelf life. 
- Save


##Data Sharing

###Metadata & Citation
- **Citation:** USAID. Office of Transition Initiatives. Information Collection and Monitoring program. Areas of Control in Syria” Created by Navanti group.
- **Description:**
  - *Abstract:* This data portrays areas in Syria controlled by various categories of armed actors according to open source intel research reports.
  - *Purpose:* This data is intended to add contextual information to reports of the crises in Syria. The data is for cartographic purposes. It is strongly recommend that this data is not used as the sole basis for making programmatic or logistical decisions.

###Distro
Email maps (both Syria and Syria/Iraq) to the following upon completion. **[Data]** indicates sharing data too:
- OTI Syria DC listserv (dcha.otisyriadcteammaillist@usaid.gov)
- Chris Williams @ DCHA Syria Task Force (cwilliams@usaid.gov)
- Hila Hanif @ OTI via DoD (hhanif@usaid.gov)
- Macey Stapleton (mstapleton@icamprogram.com) 
- Adam O'Brien (aobrien@usaid.gov)
- Chris Koltalo @ OFDA GIU (mechr_gio@ofda.gov and ckoltalo@ofda.gov) **[Data]**
- Steve Gilbert @ USAID ME (stgilbert@usaid.gov) **[Data]**
- START KMT:
  - 	Leslie Thompson (ThompsonL2@state.gov) **[Data]**
- State HIU: **[Data]**
  - Benson Wilder (wilderbf@state.gov)
  - Erika Nunez (NunezEK@state.gov)
  - Tom Gertin (GertinTJ@state.gov)
  - Dennis King (KingDJ2@state.gov)
  - Erin Sawyer (SawyerEA@state.gov)
  - Christine Fellenz (FellenzCL@state.gov)
  - Stephanie Bartlett (BartlettSH@state.gov)
- Congressional Research Service CRS: **[Data]**
  - Christopher Blanchard (cblanchard@crs.loc.gov)
  - Hannah Fischer (hfischer@crs.loc.gov)

Listed here for easy copy paste into email:

`dcha.otisyriadcteammaillist@usaid.gov, cwilliams@usaid.gov, hhanif@usaid.gov, mechr_gio@ofda.gov, stgilbert@usaid.gov, aobrien@usaid.gov, mstapleton@icamprogram.com, ThompsonL2@state.gov, wilderbf@state.gov, NunezEK@state.gov, GertinTJ@state.gov, KingDJ2@state.gov, SawyerEA@state.gov, FellenzCL@state.gov, BartlettSH@state.gov, hfischer@crs.loc.gov, cblanchard@crs.loc.gov`

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
