# Select all "wide" activities in QGIS

*How to select all regional or "wide" activities in QGIS to delete them*

With your activity shapefile in QGIS open attributes and select the "select features by exression button"

Enter this as the expression:
`regexp_match("Place",'-wide$')`
