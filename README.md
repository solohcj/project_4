# West Nile Virus Prediction for Chicago
Analyzed datasets and predicting whether or not West Nile virus is present, for a given time, location, and species.

Every year from late-May to early-October, public health workers in Chicago setup mosquito traps scattered across the city. Every week from Monday through Wednesday, these traps collect mosquitos, and the mosquitos are tested for the presence of West Nile virus before the end of the week. The test results include the number of mosquitos, the mosquitos species, and whether or not West Nile virus is present in the cohort.

## EDA

## Feature Engineering

## Modelling

## Executive Summary

## File list


### Assets file descriptions
**train.csv, test.csv - the training and test set of the main dataset.**    
- The training set consists of data from 2007, 2009, 2011, and 2013
- While in the test set you are requested to predict the test results for 2008, 2010, 2012, and 2014.   

|Feature |Description |
|:-----|:-----|
| Id | The id of the record (not shown in train dataset) |
| Date | Date that the WNV test is performed |
| Address | Approximate address of the location of trap. This is used to send to the GeoCoder |
| Species | The species of mosquitos |
| Block | Block number of address |
| Street | Street name |
| Trap | Id of the trap |
| AddressNumberAndStreet | Approximate address returned from GeoCoder |
| Latitude | Latitude returned from GeoCoder |
| Longitude | Longitude returned from GeoCoder |
| AddressAccuracy | Accuracy returned from GeoCoder |
| NumMosquitos | Number of mosquitoes caught in this trap (not shown in test dataset)|
| WnvPresent | 1: West Nile Virus is present   <br/>  0: West Nile Virus not present (not shown in test dataset)|   

**spray.csv**
- GIS data of spraying efforts in 2011 and 2013   

|Feature |Description |
|:-----|:-----|
| Date | Date of the spray |
| Time | Time of the spray |
| Latitude | Latitude of the spray |
| Longitude | Longitude of the spray |   

**weather.csv**
- weather data from 2007 to 2014     

|Feature |Description |
|:-----|:-----|
| Station | 1: Chicago O' Hare International Airport (Lat: 41.995 Lon: -87.933 Elev: 662 ft. above sea level) <br/> 2: Chicago Midway International Airport (Lat: 41.786 Lon: -87.752 Elev: 612 ft. above sea level) |
| Time | Time of the spray |
| Latitude | Latitude of the spray |
| Longitude | Longitude of the spray |  
| Date | Date |
| Tmax | Maximum Temperature in Fahrenheit|
| Tmmin | Minimum Temperature in Fahrenheit|
| Tavg | Average Temperature in Fahrenheit|
| Depart | Departure from Normal Temperature in Fahrenheit|
| DewPoint | Average Dew Point in Fahrenheit where the atmospheric temperature (varying according to <br/> pressure and humidity) below which water droplets begin to condense and dew can form.|
| WetBulb | Average Wet Bulb temperature in Fahrenheit read by a thermometer covered in <br/>  water-soaked cloth (wet-bulb thermometer)|
| Heat | Heating days (Season begins with July) |
| Cool | Cooling days (Season begins with January)|
| Sunrise | 24 hours clock, calculated not observed |
| Sunset | 24 hours clock, calculated not observed |
| CodeSum | +FC - Tornado//Waterspout <br/> FC - Funnel Cloud <br/> TS - Thunderstorm <br/> GR - Hail <br/> RA - Rain <br/> GS -  Small Hail &/Or Snow Pellets <br/> PL - Ice Pellets <br/> IC - Ice Crystals <br/> FG+ - Heavy Fog (FG & LE.25 Miles Visibility) <br/> FG - Fog <br/> BR - Mist <br/> UP - Unknown Precipitation <br/> HZ - Haze <br/> FU - Smoke <br/> VA -  Volcanic Ash <br/> DU - Widespread Dust <br/> DS - Duststorm <br/> PO - Sand/Dust Whirls <br/> SA - Sand <br/> SS -  Sandstorm <br/> PY - Spray <br/> SQ - Squall <br/> DR - Low Drifting <br/> SH - Shower <br/> FZ - Freezing <br/> MI - Shallow <br/> PR - Partial <br/> BC - Patches <br/> BL - Blowing <br/> VC - Vicinity ( - Light, + Heavy) <br/> "No Sign" Moderate


**sampleSubmission.csv**   

- a sample submission file in the correct format   


### Dataset file description

**Final dataset used for modelling**  

| Feature             | Type          | Description                                                 |
|:--------------------|:--------------|:------------------------                                    |
| Species             | Categorical   | OneHotEncoded the different species                         |
| Cluster             | Categorical   | Cluster created by pairing Latitude and Longitutde together |
| Months              | Categorical   | OneHotEncoded the different months present                  |
| Tmax                | Numerical     |                                                             |
| Tmin                | Numerical     |                                                             |
| Tavg                | Numerical     |                                                             |
| Depart              | Numerical     |                                                             |
| DewPoint            | Numerical     |                                                             |
| WetBulb             | Numerical     |                                                             |
| Heat                | Numerical     |                                                             |
| Cool                | Numerical     |                                                             |
| PrecipTotal         | Numerical     |                                                             |
| StnPressure         | Numerical     |                                                             |
| SeaLevel            | Numerical     |                                                             |
| ResultSpeed         | Numerical     |                                                             |
| ResultDir           | Numerical     |                                                             |
| AvgSpeed            | Numerical     |                                                             |
| WnvPresent          | Categorical   | Target variable - y                                         |

### Codes file description   

-
