# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Ames Housing Sale Price Prediction
   ---
  *By Ethan Koh, 4 May 2020*
### Overview and Problem Set
The property market is not for the ill-informed. Housing prices can be cruelly volatile as they can get affected by multiple factors. Every buyer and seller of a house seek to equip with better knowledge to achieve a reasonable transaction price. Even though it's not possible for every contributing factor to be captured by our dataset, given the housing dataset in Ames, we are going to create a __regression model predicting the sale price of houses in Ames, Iowa__. In addition, we will be able to discover what are the main factors contributing to the price.

### Datasets
These datasets are provided by General Assembly for our course Kaggle competition. The dataset was prepared by Dean De Cock taken from the Ames, Iowa Assessor’s Office, originally used for tax assessment purpose. Data set contains information used in computing assessed values for individual residential properties sold in Ames, Iowa from 2006 to 2010.

The data by Dean De Cook has 2051 observations and 82 columns which include 23 nominal, 23 ordinal, 14 discrete, and 20 continuous variables, and 2 additional observation identifiers. However, data given by General Assembly has 81 columns, with 'Sale Condition' variable excluded, which include 22 nominal, 23 ordinal, 14 discrete, and 20 continuous variables, and 2 additional observation identifiers.

- train.csv <br /> 
- test.csv <br />

## Data Dictionary

[LINK](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

## Assumptions and Limitations
Using multi-linear regression has it's own assumptions:<br />
Firstly, the predictors and target variable have an approximate linear relationship.<br />
Secondly, residuals are independent of each other, following a Normal distribution with mean 0 and have roughly equal variances.<br />
Thirdly, the predictors are independent of each other.<br />

In addition, there are limitations to predict future prices based on a 2006-2010 old dataset that we have. Many of the predictors for sale price may no longer be significant/relevant. Example, neighbouhood or street may have expanded.

## Table of Contents
- Import Libraries<br /> 
- Load Dataset<br />
- Data Cleaning: Missing Data <br /> <ul>
- Left 4 predictors with missing values
- Missing values actions to take 
- Filling missing values</ul>
- Exploratory Data Analysis<br /> <ul>
- Datatypes Correction
- Remove outliers
- Correlation
- Feature Selection</ul>
- Feature Engineering: Interaction terms
- Drop columns
- Data Conversion: String to integer
- Convert Categories to Integers via get_dummies
- Model Prep
- Select Hyperparameters<ul>
- Lasso Regression
- Elastic Regression
- Refine Elastic Regression</ul>
- Baseline model
- Scaling
- Model Selection, Fitting and Evaluation
- Kaggle Submission