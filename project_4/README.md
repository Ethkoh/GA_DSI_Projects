# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 4: West Nile Virus Prediction
   ---
  *By Ethan Koh,
      Grace Chia,
      Jocelyn Pok,
      Randy Neo,                    5 June 2020*
      
## Background
West Nile Virus (WNV) is usually spread to humans through infected mosquitos. Around 20% of individuals who become infected with the virus develop symptoms ranging from a persistent fever, to serious neurological illnesses that can result in death.

In 2002, Chicago recorded it's first human incident of West Nile virus. By 2004 the City of Chicago and the Chicago Department of Public Health (CDPH) had built a comprehensive surveillance and control program that is still in effect today.

Every week from late spring through the fall, mosquitos in traps across the city are tested for the virus. The results of these tests influence when and where the city will spray ariel pesticides to reduce adult mosquito populations. Every week from Monday through Wednesday, these traps collect mosquitos, and the mosquitos are tested for the presence of West Nile virus before the week ends. The test results include the number of mosquitos, the mosquitos species, and whether West Nile virus is present in the cohort.

This project is from: https://www.kaggle.com/c/predict-west-nile-virus/overview.

## Problem Statement
Due to a recent outbreak of the West Nile Virus in the city of Chicago, the Data Science team at the Disease and Treatment Agency has been tasked by the Centers for Disease Control (CDC) to develop a strategy to deploy the effective use of pesticides. Targeting spraying efforts to areas of high risk will help to mitigate future outbreaks.

Leveraging on weather, location, mosquito population and spraying data, we will build a binary classification model that predicts the presence of the West Nile Virus in the city of Chicago. The model that achieves the highest ROC AUC score on the validation set, will be selected as our production model. The model is also expected to outperform the baseline ROC AUC score of 0.5. A cost-benefit analysis will also be done to determine if the benefits of spraying outweighs its costs.

## Executive Summary
Out of all the classification models built, XGBoost was selected as it achieved the highest ROC AUC score on the validation set. The model attained an ROC AUC of 0.83 on the validation set, outperforming the baseline score of 0.5. As observed from the model's feature importance, it turns out that seasonality plays a very key role in mosquito breeding and the spread of WNV, with 'month' being the most important predictor. Besides other sesonality features like 'week' and 'day', 14-day rolling weather conditions like wetbulb, dewpoint and temperature are also key in predicting the presence of WNV in the City of Chicago. The model received a 0.76 ROC AUC score on Kaggle.

Based on the cost benefit analysis, spraying at areas with more than 12 WNV cases overweighs the cost of the spray, suggesting that spraying at those areas is the most cost effective solution. In addition, reduction in cost of 1 WNV case overweights the spraying of of 10km² area.

As the model performs relatively well on unseen data, the Disease and Treatment Agency will now be able deploy pesticide-spraying efforts to areas of high risk. An efficient allocation of resources will help help to clamp down on the WNV outbreak, reducing residents' exposure to the virus.

## Code 
- Data_Cleaning_EDA.ipynb<ul>
- Import Libraries
- Load Data
- Data Cleaning
- Feature Engineering
- EDA
- Prepare Train and Test Set</ul>

- Modeling.ipynb<ul>
- Import Libraries
- Load Data
- Modelling
- Model Evaluation
- Cost Benefit Analysis
- Conclusion and Recommendations</ul>

## Data Sets
- **Train and Test data**<br/>
The training set consists of data from 2007, 2009, 2011, and 2013, while in the test set you are requested to predict the test results for 2008, 2010, 2012, and 2014. Not all the locations are tested at all times. Also, records exist only when a particular species of mosquitoes is found at a certain trap at a certain time.

|Feature|Description|
|---|---|
|Id| the id of the record|
|Date| date that the WNV test is performed|
|Address| approximate address of the location of trap. This is used to send to the GeoCoder |
|Species| the species of mosquitos|
|Block| block number of address|
|Street| street name|
|Trap| Id of the trap|
|AddressNumberAndStreet|approximate address returned from GeoCoder|
|Latitude, Longitude| Latitude and Longitude returned from GeoCoder|
|AddressAccuracy| accuracy returned from GeoCoder|
|NumMosquitos| number of mosquitoes caught in this trap|
|WnvPresent|whether West Nile Virus was present in these mosquitos. 1 means WNV is present, and 0 means not present|

- **Map Data**<br/>
The map files mapdata_copyright_openstreetmap_contributors.rds and mapdata_copyright_openstreetmap_contributors.txt are from Open Streetmap,primarily provided for use in visualizations.
<br/><br/>
- **Weather Data** <br/>
NOAA's National Centers for Environmental Information (NCEI)<sup>2</sup> is responsible for preserving, monitoring, assessing, and providing public access to the Nation's treasure of climate and historical weather data and information.<br/>
This dataset contains weather conditions from NOAA from months of 2007 to 2014. <br/>
The stations captured:<br/>
Station 1: Chicago O'hare International Airport :<br/>Lat: 41.995 Lon: -87.933 Elev: 662 ft. above sea level <br/>
Station 2: Chicago Midway Intl Arpt :<br/>Lat: 41.786 Lon: -87.752 Elev: 612 ft. above sea level.<br/>
Column descriptions are in noaa_weather_qclcd_documentation.pdf. 
<br/><br/>
- **Spray Data**<br/>
Geographic Information Systems (GIS) data of spraying efforts in 2011 and 2013 to reduce the number of mosquitos in the area, and therefore thus reduce the presence of West Nile virus. 

|Feature|Description|
|---|---|
|Date, Time|date and time of the spray|
|Latitude, Longitude| the Latitude and Longitude of the spray|

- **Sample Submission**<br/>
A sample submission file in the correct format for kaggle submission. For each Id in the test set, we should predict a real-valued probability that WNV is present. 

