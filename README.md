# StopQuestionFrisk

## 0. Data preparation and inspection

#### SOURCES

* Stop-and-frisk (SQF) data from NYPD, 2019 and 2020. 
     https://www1.nyc.gov/site/nypd/stats/reports-analysis/stopfrisk.page

* Census data (demographics etc.) from the American Community Survey (ACS) 2014--2019, downloaded using
the `tidycensus` package:
    https://walker-data.com/tidycensus/articles/spatial-data.html

* Census tract shapefiles 2019 from US Census: 
    https://www.census.gov/cgi-bin/geo/shapefiles/index.php?year=2019&layergroup=Census+Tracts trimmed to the New York state
shoreline: 
     http://gis.ny.gov/gisdata/inventories/details.cfm?DSID=927

#### PREPARED DATASETS

*  `tracts`:
    one row per census tract
    (excluding two entirely-aquatic census tracts, which have been removed).
    The shape of each tract is included.
    (All geo coordinates are in EPSG 2908, the State Plane Coordinate System for NY/LongIsland.)

* `census`:
    one row per census tract, excluding the two aquatic tracts

* `sqf`:
    one row per stop-and-frisk incident, spanning 2019 and 2020, labelled by census tract
    (except for four records in 2020 with nonsense locations, which have been removed)