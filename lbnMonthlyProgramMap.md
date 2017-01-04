# Lebanon Monthly Program Map 

## Background
Lebanon has two versions of their _Monthly Program Map_: 
- _Internal_ 
  - Uses selectable layers
  - Distinguishes between program objectives
  - UNHRC Vulnerability Layer
  - Dominant Religion Layer
  - Vulnerability x Dominant Religion Layer
  
- _External_
  - UNHRC Vulnerability Layer

## Steps
- Download the geospatial report for this month's map

- Run the Lebanon Dissolve Script

- A new folder with the YYYYMM should be created with three subdirectories
  - csvs: updated csv of the activities and the original geospatial report are stored here
  - paperTrail: `.txt` document of activity status counts and Estimated Amount Totals as well as objective totals and activity counts
  - shps: 2 subdirectories containing dissolves with and without distinguishing obejectives

- Save SHPs in`Q:\GIU_Workspace\Country\Lebanon\OTI_Data\Activities\YYYYMM`

- Open OTI_Lebanon_Program_Religion_Vulnerability_DFv10.3

- Add the `misYYYYMMdiss.shp` from the dissolveWithObj folder and copy the layer again

- Right Click on the Layer and select Properties and then select the Definition Querry Tab

- Write the following queries on one of the duplicate layers:
  - `"OBJECTIVE" = 'I. Mitigate Rising Sectarian and Host Community-Refugee Tensions'`
  - `"OBJECTIVE" = 'II. Counter the influence of violen extremist groups`
  
- In the Symbology tab of Layer Properties import the previous month's style and make any necessary adjustments to the symbol ranges or the number of symbols.

- Copy the two layers to the Tripoli inset
  

