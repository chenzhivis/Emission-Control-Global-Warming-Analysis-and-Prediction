# Global-Warming-Analysis-and-Prediction

## Brief background
Global warming is a top topic of common concern. It is important to understand how is earth surface temperature changing, the trend and to predict, which has guiding significance to many fields (agriculture, energy-efficiency, emmission control, restructuring energy industry, etc). To predict future earth surface temperature can be pure time series problem, but global warming is also related to other factors, such as greenhouse gases emission, human activities, etc. In this project, I used various time series models, cointegration & granger causality analysis to analyze the earth surface temperature change, develop a model to predict future temperature and also analyze how other features (CO2, population) influence the global warming.

## Goals of this project: 

(1) establish a model that can predict earth surface temperature based on time series;

(2) improve the forecasts by various models and by multivariate times series technics (exogenous features, cointegration, Granger causality analysis, VECM, additional regressors, etc); 

(3) analyze the relationship between temperature and various factors; 

(4) try to reach to a conclusion regarding how various factors affect the global warming trend.

## Resources of data:

(1) earth surface temperature dataset from kaggle.com

(2) web scraping global population data and global urban population data from www.johnstonsarchive.net

(3) carbon dioxide concentration data from esrl.noaa.gov  

## This repository contains the following files:

*  globalwarming.ipynb, -- the main jupyter notebook of this project, containing 6 parts: 
1. Data collection and cleaning
2. Exploratory Data Analysis, statistics, relevant social and environment analysis
3. Preprocessing
4. Various models, ARIMA, SARIMAX, Grid Search
5. Cointegration analysis and tests -- foundation of exogenous variables
6. Model improving -- ARIMAX with exogenous features, Grid Search
7. Granger Causality analysis and explanation -- foundation of multivariates
8. More models -- Vector Auto Regression (VAR) and Grid Search for multivariate time series
9. More models -- Vector Error Correction Model (VECM) and Grid Search for multivariate time series
10. More models -- Fbprophet
11. Conclusions

*  webscraping.ipynb, -- the coding jupyter notebook for web scraping population data from www.johnstonsarchive.net

*  'pop.csv' -- world population data from year

*  'ur.csv' -- urban population data from year

*  'GlobalTemperatures.csv'  -- earth surface temperature data

*  'co2-annmean-mlo.csv' -- annual carbon dioxide concentration data

*  'co2-mm-mlo_csv.csv' -- monthly carbon dioxide concentration data

*  'co2history.csv' -- historical carbon dioxide data concentration data


## Some conclusions: 

### Third industrial revolution time (1950s) is watershed for global warming:

Analysis showed that the third industrial revolution time (1950s) is a watershed. Before third industrial revolution, the earth surface temperature increased slowly, only 8% over 200 years. But after third industrial revolution, earth surface temperature increased another 12% for recent 60 years. Coincidentally, carbon dioxide concentration increase also accelerate after 1950s. Between 1750s to 1950s, the carbon dioxide concentration in air only increased around 12%, but from 1950s to 2010s, it raised another 30%. This is a hint that carbon dioxide concentration rising is related to earth surface temperature. Carbon dioxide is the major greenhouse gas that contribute to global warming, most people believe so although it not 100% sure that carbon dioxide emission caused the global warming. 

A graph is shown as following: 

![image](https://user-images.githubusercontent.com/64159084/89968826-e5c34580-dc22-11ea-8502-5909935cd723.png)

### Best models in this project are ARIMAX with exogenous variables and VECM:

The main reasons that ARIMAX model with exogenous variables(CO2 and urban population) and VECM work better in this case than ARIMA, SARIMAX, VAR and FBprohet is:
(1) Based on the nature of this case described in Section 11.3 in globalwarming.ipynb, it makes more sense to use CO2 and urban population as exogenous variables to assist forecast of temperature, rather than making them all to be equivalently interactive series in a VAR model;
(2) Combining stationary levels (VECM imposes additional restriction due to the existence of non-stationary but co-integrated data forms and utilize co-integration restriction infromation of the 3 time series) and differences from all time series in VECM also make more sense than making them all to be equivalently interactive series in a VAR model;
(3) Ignoring the information that CO2 time series and urban population time series provide (ARIMA models) definitely reduce the accuracy of the modeling. And, treating CO2 time series and urban population time series as additional regressors (Fbprophet) does not make sense as (1) and (2).
(4) The yearly earth surface temperature time series don't have seasonality, so SARIMAX model does not improve results.

please check out the prediction of the earth surface temperature for 53 years: 
![image](https://user-images.githubusercontent.com/64159084/91113211-004de380-e653-11ea-87d7-9d2a2970b6e8.png)

### CO2 concentration change and world urban population change influenced earth surface temperature change:

Cointegration analysis and Granger Causality analysis show that CO2 concentration in air has strong influence to the earth surface temperature change (it is not scientifically rigorous to conclude that CO2 concentration cause the global warming, but from my statistical analysis, CO2 concentration greatly influenced temperature raising). When it comes to population, analysis in this project show that world population does not directly influence the earth surface temperature, but the world's urban population has influence to earth surface temperature change.

## Project presentation link:

https://docs.google.com/presentation/d/181Kq0P_UphGJjV9j2gTVnUUjM4On7hDtWYTgI2cVjgM/edit?usp=sharing

