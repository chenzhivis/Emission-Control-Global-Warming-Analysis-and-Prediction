# Global-Warming-Analysis-and-Prediction

## Brief background
Global warming is a top topic of common concern. It is important to understand how is earth surface temperature changing, the trend and to predict, which has guiding significance to many fields (agriculture, energy-efficiency, emmission control, restructuring energy industry, etc). To predict future earth surface temperature can be pure time series problem, but global warming is also related to other factors, such as greenhouse emission, human activities, etc. In this project, I am trying to analyze the earth surface temperature trend, develop a model to predict future temperature and also analyze how another features (CO2, population) influence the global warming.

## Goals of this project: 

(1) establish a model that can predict earth surface temperature based on time series;

(2) improve the model by multivariate method or with various exogenous features (carbon dioxide concentration, world population, world urban population); 

(3) analyze the relationship between temperature and various factors; 

(4) try to reach to a conclusion regarding how various factors affect the global warming trend.

## Resources of data:

(1) earth surface temperature dataset from kaggle.com

(2) web scraping global population data and global urban population data from www.johnstonsarchive.net

(3) carbon dioxide concentration data from esrl.noaa.gov  

## This repository contains the following files:

*  globalwarming.ipynb, -- the main jupyter notebook of this project, containing 6 parts: 
1. Data collection and cleaning
2. Explanatory Data Analysis, statistics, relevant social and environment analysis
3. Preprocessing
4. Time series modeling and evaluation
5. Cointegration tests
6. Conclusions
7. Model improving

*  webscraping.ipynb, -- the coding jupyter notebook for web scraping population data from www.johnstonsarchive.net

*  'pop.csv' -- world population data from year

*  'ur.csv' -- urban population data from year

*  'GlobalTemperatures.csv'  -- earth surface temperature data

*  'co2-annmean-mlo.csv' -- annual carbon dioxide concentration data

*  'co2-mm-mlo_csv.csv' -- monthly carbon dioxide concentration data

*  'co2history.csv' -- historical carbon dioxide data concentration data


## Some conclusions: 

### Third industrial revolution time (1950s) is watershed for global warming:

Analysis showed that the third industrial revolution time (1950s) is a watershed. Before third industrial revolution, the earth surface temperature increased slowly, only 8% over 200 years. But after third industrial revolution, earth surface temperature increased another 12% for recent 60 years. Coincidentally, carbon dioxide concentration increase also accelerate after 1950s. Between 1750s to 1950s, the carbon dioxide concentration in air increased around12%, but from 1950s to 2010s, it raised another 30%. This is a hint that carbon dioxide is related to earth surface temperature. Carbon dioxide is the major greenhouse gas that contribute to global warming, most people believe so although it not 100% sure that carbon dioxide emission caused the global warming. 

A graph is shown as following: 

![image](https://user-images.githubusercontent.com/64159084/89968826-e5c34580-dc22-11ea-8502-5909935cd723.png)

### Very good forecast results can be given by ARIMA:

Using time series modeling (ARIMA and SARIMAX), earth surface temperature can be relatively accurately forecasted. In section 4, metrics mean absolute error, mean square error and root mean square error were used to evaluate forecast results. The best result for 11 years forecast gave MSE: 0.016, RMSE: 0.128 and MAE: 0.102. Comparing to real observations value around 9 celcius from 2004 to 2015, this error is very tiny.

### CO2 concentration change and world urban population change are related to earth surface temperature change:

Coint and Johansen tests showed that there is correlation between earth surface temperature raise and carbon dioxide concentration raise. And there may also be correlation between earth surface temperature and world urban population (number of observations are limited since world population data does not contain data before 1950). These are consistent with explanatory analysis in project. The world total population and rural population raise are not considered correlated to earth surface temperature raise as shown by hypothesis tests.

## Project presentation link:

https://docs.google.com/spreadsheets/d/1pmSGwP-IvdLDpKhyXfn7sl3eWXwaCsxy-7t5gjiHA9c/edit#gid=601231408

