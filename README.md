# Electric-Consumption-prediction

<img src="image/light-bulbs.jpeg" width="600px">

The original data can be found [here](https://www.eia.gov/consumption/residential/data/2009/index.php?view=mic).

## Background 
This 2009 version represents the 13th iteration of the RECS program. First conducted in 1978, the Residential Energy Consumption Survey is a national sample survey that collects energy-related data for housing units occupied as a primary residence and the households that live in them. Data were collected from 12,083 households selected at random using a complex multistage, area-probability sample design. The sample represents 113.6 million U.S. households, the Census Bureau’s statistical estimate for all occupied housing units in 2009 derived from their American Community Survey (ACS).

## Objective
The objective is to predict the residential electric consumption in the U.S in 2009.

## Approach:
1. Data Cleaning
    - Anomaly Detection
    - Data Wrangling (identifying feature types)
    - Multicolinearity
2. Data Modeling
    1. Process the data for modeling
        - Drop irrelevent features
        - One-hot encoding the categorical features
        - Scale the numerical feature values to a uniform range
    2. Machine learning models applied:
        - OLS Linear Regression
        - Ridge Regression
        - Lasso Regression
        - Decision Tree
        - Random Forest
        - Voting Ensemble
    3. Hyperparameter tunning
    4. Feature importance
3. Model evaluation
   - Compare RMSE for the best performing models (Ridge, Lasso, Voting Ensemble)
   - Choose Ridge regression as the best model(RMSE of Ridge regression: `2.0`)
   
## Analysis Write-Up
**From the variable importance sections:**

1. The variable TOTALBTUOTH seem to be the most important and influential variable. This make sense because the total usage for appliances, electronics, lighting, and miscellaneous uses should be the major electricity consumptions
2. There are interesting findings that natural gas (CUFEETNGOTH), fuel oil (GALLONFO) propane (GALLONLPOTH) usages have a negative relationship with KWH. That means, if the household use more gas, fuel or propane then they are more likely to use less electricity. This means that these energies are alternative options for the households to live.
3. The other variables are expected to be in the model, such as the electricity usage for different kind of purposes. 

**Future work:**

1. collecting seasonal electricity usage might be useful for predicting KWH.
2. training some more complex models might also be useful (eg. random forest, xgboost)
3. using some advance imputing missing value method could also be helpful

**Conclusion:**
* Ridge regression did a great job predicting KWH with RMSE around 2.0. This is simple model, fast to train, and easy to interpret. 

