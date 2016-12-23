[NOAA](https://www.ncdc.noaa.gov/cdo-web/) Climate Data Online (CDO) provides free access to NCDC's archive of global historical weather and climate data in addition to station history information. These data include quality controlled daily, monthly, seasonal, and yearly measurements of temperature, precipitation, wind, and degree days as well as radar data and 30-year Climate Normals. 

## Purpose of the scriptr.io connector for NOAA
The purpose of this connector is to simplify and streamline the way you access NOAA' APIs from scriptr.io, by providing you with a few native objects that you can directly integrate into your own scripts.


## Components
- NOAA/config : a configuration file that contains token that the developer purchase from [NOAA](https://www.ncdc.noaa.gov/cdo-web/token)

- NOAA/dataCategories : this object have two methods that will return Data Categories that represent groupings of data types.(getDataCategories(),getDataCategoriesFromId())

- NOAA/dataSets : this object have two methods that will return All of the CDO datasets. The containing dataset must be known before attempting to access its data.(getDataSets(),getDataSetsFromId(),getData())

- NOAA/dataTypes : this object have two methods that will describe the type of data, acts as a label. If it's 64°f out right now, then the data type is Air Temperature and the data is 64.(getDataTypes(),getDataTypesFromId())

- NOAA/locations : this object have two methods that will return a specific latitude/longitude point such as a station, or a label representing a bounding area such as a city.(getLocations(),getLocationsFromId())

- NOAA/LocationCategories : this object have two methods that will return groupings of locations under an applicable label.(getLocationCategories(),getLocationCategoriesFromId())

- NOAA/stations : this object have two methods that will return Stations information where the data comes from (for most datasets) and can be considered the smallest granual of location data. If the desired station is known, all of its data can quickly be viewed representing a bounding area such as a city.(getStations(),getStationsFromId())

## How to use
- Use the Import Modules feature to deploy the aforementioned scripts in your scriptr account, in a folder named "modules/NOAA".
- Create a developer account and an application at [NOAA](https://www.ncdc.noaa.gov/cdo-web/).
- Once done, make sure to specify the NOAA token in "config" file ("token") .
- Create a test script in scriptr, or use one of the scripts provided in modules/NOAA/test/. 
