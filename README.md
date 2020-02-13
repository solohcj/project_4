# West Nile Virus Prediction for Chicago

## Scope
1. Background
2. Problem Statement
3. Executive Summary
Project Planning
4. EDA
5. Feature Engineering
6. Modeling
7. Cost-Benefit Analysis
8. Conclusion and Recommendations
9. Assets File Descriptions
10. Dataset File Descriptions
11. Codes File Descriptions

## Background
West Nile Virus is most commonly spread to humans through infected mosquitos. Due to the recent epidemic in City of Chicago, Chicago Department of Publich Health (CDPH) had established a surveillance and control program. The program entails setting mosquito traps, testing for WNV and spraying of airborne pesticides in the city.

Every year from late-May to early-October, CDPH setup mosquito traps scattered across the city. Every week from Monday through Wednesday, these traps collect mosquitos, and the mosquitos are tested for the presence of West Nile virus before the end of the week. The test results include the number of mosquitos, the mosquitos species, and whether or not West Nile virus is present in the cohort.

Centres for Disease Control and Prevention (CDC) has engaged Disease and Treatment Agency (DATA) for the following services:
- To conduct a review on the surveillance and control program through data analytics
- To conduct a cost-benefit analysis on the annual cost projections for various levels of pesticide coverage and  the effect of of these various levels of pesticide coverage

DATA is responsible to analyze the mosquito trap location, testing and spraying datasets given by CDPH, and weather datasets given by National Oceanic and Atmosphere Administration (NOAA) to predict whether or not West Nile virus is present, for a given time, location, and species.

## Problem Statement

- To build a model and make predictions on the probability that WNV is presesent so as to aid CDC in deriving an effective pesticide deployment plan
- To conduct a cost-benefit analysis on the annual cost projections for various level of pesticide coverage and the effects of these various levels of pesticide coverage

## Executive Summary

## Project Planning
- Project Milestones: https://github.com/Zoeychengg/project_4/milestones
- Task Breakdown: https://github.com/Zoeychengg/project_4/projects/1

## EDA
  
## Feature Engineering

## Modeling

## Cost-Benefit Analysis

## Executive Summary

## File List


### Assets File Descriptions
**train.csv, test.csv - the training and test set of the main dataset.**    
- The training set consists of data from 2007, 2009, 2011, and 2013.
- The test set used to predict the results are from 2008, 2010, 2012, and 2014.

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
| Tmin | Minimum Temperature in Fahrenheit|
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


### Dataset File Descriptions

**Final dataset used for modelling**  

| Feature             | Type          | Remarks                                                 |
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

### Codes File Descriptions

1. Cleaning and EDA
2. Modeling
3. Cost-Benefit Analysis
