#QG2Web: Using the QGIS 2 Web Plugin

##INTRO
Walk you through all aspects of the QGIS 2 Web plugin

##Installation
In the plugins menu search for QGIS2Web plugin and install through the 'manage and install plugins' toolbar.
Once installed an 'export to openlayers' option will appear in the plugins menu.

##Formatting HTML popup box
In order for text to properly display in leaflet it should be formatted as html but usually spatial data is tabular. 
This documents the process of concatinating text from various columns of geospatial data into one field as a string with html formatting.

*Note* We will be using ACLED data as an example 

1. Download ACLED data and open in excel. 
2. Add column to end named html_exp 
3. Concatinate all relevant fields wrapping text in html tags like so: 
```
=CONCATENATE("<h3>",F2,"</h3><table>", "<tr><td>Location: <b>",R2, "</b></td></tr><tr><td>Actor: <b>",G2,"</b></td></tr><tr><td>Fatalities: <b>",X2, "</b></td></tr><tr><td>Date: <b>",C2,"</b></td></tr></table><p>",W2,"</p><br>Source: <b>",V2,"</b>")
```
Once you load into QGIS and export the popup should render the html popup properly.
