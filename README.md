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



### Accuracy and F1 score metrics are appropriate in this project:

The metrics we used to evaluate our models are the accuracy score and weighted f1 score, as shown in section 4. We have 8 categories of negative reviews (RudeService, SlowService, OrderProblem, BadFood, BadNeighborhood, Filthy, MissingFood and Cost) in this case, and they are highly imbalanced (the major 2 classes are 'RudeService' and 'SlowService' and account for 52% of all negative reviews; while the minor classes, 'MissingFood' or 'Cost' for example, account for just around 2% of all negative reviews). In our case, after thorough discussion, we are not leaning to any specific class. Although BadNeighborhood and Cost problems may not be easily solved by the restaurant manager, all other classes are very important from management point of view. So precision and recall are not what we prioritized as our evaluation metrics. We used an accuracy score and a weighted f1 socre as metrics to evaluate models. We used weighted f1 score because we want to take the class imbalance into account, and calculate the metric for each label and find their average weighted by support(number of true predictions for each class label).

### Stemming works better than lemmatization in this review data case:

The way we preprocess the data really has an influence on prediction. The way the corpus is preprocessed will differentiate the results. For example, in this project, we found out that stemming works better than lemmatization while normally lemmatization will do a better job than stemming. This is because we are dealing with Yelp reviews. When writing Yelp reviews, many people do not pay attention to proper grammar rules, some times not even completing words, they don't fully complete their sentances and they are trying to write as simple as possible as long as they can express their dissatisfaction. In this particular case, it makes sense that stemming works better. Thus, in NLP, data scientists shall firstly look into the corpus, understand how the texts look like and then determine which preprocessing steps make sense.

### The classifier model developed in this project can be used to classify negative reviews of similar fast food restaurant (KFC, Burger King, etc), here is a sample classification of KFC reviews (data from Yelp API): 

![Screen Shot 2020-07-30 at 9 30 22 PM](https://user-images.githubusercontent.com/64159084/88990479-0945d200-d2ac-11ea-9801-380a966aab86.png)

## Project presentation link:

https://docs.google.com/spreadsheets/d/1pmSGwP-IvdLDpKhyXfn7sl3eWXwaCsxy-7t5gjiHA9c/edit#gid=601231408

