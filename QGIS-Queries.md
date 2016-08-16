
With your activity shapefile in QGIS open attributes and select the "select features by exression button"

## Select all "wide" activities in QGIS
`regexp_match("Place",'-wide$') or "Place" = 'National'`

## Select all Cleared Closed Completed activities in QGIS
`"status" =  'Cleared' or "status" =  'Closed'`
