
# Zillow Regression Project for Tax Value Prediction of Single Family Residential Properties
- Rajaram Gautam           - December 13, 2021          - Submitted To: Zillow Data Science Team

# Project Summary

# Business Goals
- To construct a Machine Learning Regression Model that can predict the tax value of Single Family Residential Properties using various attributes of the properties that had transaction date in 2017.
- To find key drivers of the property value for the Single Family Residential Properties.
- Deliver a report that data science team can read and understands about the procedures taken to come to conclusion.
- To make recommendation based on my works what would work and what not in the predictions of the home tax value.
- To know the county and state of the properties that had transaction in 2017.

# Executive Summary
This section after all findings


# Deliverables
- A report in the form of presnetation and live presentation of the work via zoom.
- Github Repository with a complete readme.md, a final report(.ipynb), acquire, prepare, explore, and model modules made to make workflow in project pipeline easy.
- The report will summarize the findings about the drivers of tax value of the single family residential properties with suitable visualizations.

# Intial Questions
-
-
-
-

# Data dictionary

|Index | Column Name | Description | Count | Dtype|
|---|---|---|---|---|
|0 |  bedrooms          | Number of Bedrooms                                 | 27363 non-null | int64  |
|1 |  bathrooms         | Number of bathrooms                                | 27363 non-null | float64|
|2 |  sqft              | Square footage of the house                        | 27363 non-null | int64  |
|3 |  tax_value         | Value of the property                              | 27363 non-null | float64|
|4 |  year_built        | Year property was built                            | 27363 non-null | int64  |
|5 |  tax_amount        | Tax amount per property                            | 27363 non-null | float64|
|6 |  fips              | Federal Information Processing Series (FIPS) Codes | 27363 non-null | int64  |
|7 |  zipcode           | Zipcode                                            | 27363 non-null | int64  |
|8 |  zipcode_avg_price | Average home price per zipcode                     | 27363 non-null | int64  |
|9 |  county            | County Name                                        | 27363 non-null | object |
|10|  state             | State Name                                         | 27363 non-null | object |
|11|  garage_area       | Area of Garage                                     | 27363 non-null | int64  |
|12 |  transactiondate.  | Transaction date for the property                 | 27363 non-null | int64  |

For Full Data Dictionary for Zillow database that we are using here, please follow the ling below.


# Project Specifications

# Plan:
- Single Family Residential Properties data to extracted from Zillow database provided with suitable attritues that will help us in determing tax value of the house.
- Preparare: Prepare data to ensure that data format of each attriutes selected will fit into our model, remove outliers, handle NaN in data properly using best judgement to so that our model will give give us less error.
- Explore: Explore the data for attrubte that will have possible relationship with tax value and remove the attributes in that have colinearly dependent to each other. 
- Model : We will use Linear Regression Model like Ordinar Least Squares, LASSO + LARS, Polynomial Regression Generalized Linear Model (TweedieRegressor)
- Iterate : We will iterate the process for various model with different values of model parameter to choose the best model for our test data, to make better predictions.

# Acquire
- I created a series of functions to acquire and clean the zillow data, which are located in the zillow_wrangle.py file. They take in all of the single unit properties (code 261 from the propertylandusetypeid column on the properties_2017 table in the zillow data set) that were sold between 1 May and 1 Sept of 2017 (based on the predictions_2017 table) into a Pandas dataFrame.
- I have teken a column for zipcodes and modified it to average home price per zipcode, as well as the county and sate name.

# Prep
- Top and Bottom of outliers were removed so that when we take median as baseline it will give us less error.
- Features and columns that seems to have no influence in tax value has not be extracted and even those of extracted some are removed as they seemed irrelevant.
- The remaining data, aside from the target, was scaled using a min-max scaler

# Explore
- Scatterplots with trend lines are used to look for obvious correlations.
- Boxplots are used to show the distributions and possible outliers even after preparing.
- A heatmap was generated to show correlation strength between features
- Statistical tests were used to confirm correlation between the target and other features

# Model & Evaluate
- The following models were used:
 - Baseline (using mean) # TBA
 - Ordinary Least Squares
 - LASSO + LARS
 - Generalized Linear Model
 - Polynomial 2nd Degree
 - Polynomial 3rd Degree

# Details on FIPS Code
https://www.nrcs.usda.gov/wps/portal/nrcs/detail/national/home/?cid=nrcs143_013697


### Reproduce My Project

You will need your own env file with database credentials along with all the necessary files listed below to run my final project notebook. 
- Read this README.md
- Download the wrangle.py, aquire.py, prepare.py, explore.py, evaluate.py, and final.ipynb files into your working directory
- Add your own env file to your directory. (user, password, host)
- Run the final_report.ipynb notebook

# Conclusion (TBA)
- All of the models were relatively close, but the Polynomial 3rd degree regression model produced the best results with a 20% improvement over the mean baseline model (comparing validation data). Therefore, these models do show that they could be used to produce a prediction for home values; however, the error is still high at over number RSME. Additional refining would need to be done in order to use this model as a reliable predictor of home values.

