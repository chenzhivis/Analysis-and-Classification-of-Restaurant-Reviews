# Mod4-Project
Flatiron Mod4 Project

## Brief background
It is essential for a restaurant manager to know feedbacks from clients (like what are the defects in services, how people feel about the food, etc) in order to improve the customer satisfaction and restaurants' overall business. The most important resource of feedback are guests' reviews, especially those negative reviews. However, looking through thousands of guests' reviews can too time-consuming and frustrating. Moreover, third party platform like Yelp just give ratings without information regarding why reviews are negative (type of drawbacks). Wouldn't it be perfect to have a NLP classification model that can classify different types of negative reviews for a restaurant manager before he look into those reviews?

In this project, we use a McDonald's review dataset and reviews we collected using Yelp API to analyze the negative reviews, to analyze feedbacks from McDonalds' guests and KFC guests, to give an idea about how various fast food restaurants do in different cities, and finally to establish a NLP classification model that can classify negative reviews for restaurant managers.

## Goals of this project: 

(1) analyze negative reviews and feedback from guests of fast food restaurant; 

(2) get an idea about how various fast food restaurants do in different cities (what are the different defects in services, food, etc); 

(3) develop an NLP classification model that can classify negative reviews for restaurant managers, help the manager save time on absorbing information, help restaurants improve the business. 

(4) try our model on a similar fast food restaurant's (KFC) reviews. 

(5) sell this NLP classification model to a restaurant manager for $1,000.

## Resources of data:
McDonald's review dataset from data.world: 
https://data.world/crowdflower/mcdonalds-review-sentiment

KFC restaurant reviews we collected using Yelp API. 

## This repository contains the following files:

*  mod4_project.ipynb, -- the main jupyter notebook of this project, containing 6 parts: 
1. Data collection, API and cleaning
2. Explanatory Data Analysis, descriptive statistics of reviews
3. Preprocessing & feature engineering
4. Various model fitting
5. Models evaluation
6. Business conclusion and discussion

*  mod4_API.ipynb, -- the jupyter notebook for Yelp API to get KFC restaurants reviews, clean up and to save data to .csv file

*  McDonalds-Yelp-Sentiment-DFE.csv, -- the dataset that contains 1525 observations of reviews, cities, sentiments, etc from clients who ate in McDonald's stores. 

*  kfc.csv, -- the data file we saved after getting KFC restaurants reviews data by Yelp API. This is a clean dataset. 

*  reviewclassifier.sav -- the classification model that gives best accuracy and f1 score. 

## Some conclusions: 

### The distribution of negative review classes:

Among all negative review categories, 'RudeService' and 'SlowService' are the major classes. This is shown in our reviews' statistical analysis and validated in the KFC reviews. These 2 points shall address attention of fast food restaurant managers. You cannot treat guests poorly just because you are selling fast food! Every one cares about how he/she is served regardless if they're staying for just 1 minute in fast food restaurant or 2 hours in a fancier sit-down establishment.
Recommendations: McDonald's store managers should pay close attention to employees' attitude towards guests.
SlowService is the second major complaint among customers. One of the main reasons that people choose to eat fast food is to save time. Our SlowService corpus statistics show that people are complaining about less staff, long wait time, etc.
Recommendations: Restaurant managers should arrange more staff to work during rush hours or establish a more efficient process to serve guests.

![negative_reviews](https://user-images.githubusercontent.com/64159084/88987217-3e99f200-d2a3-11ea-99a1-7cdef47e33a6.png)

### Accuracy and F1 score metrics are appropriate in this project:

The metrics we used to evaluate our models are the accuracy score and weighted f1 score, as shown in section 4. We have 8 categories of negative reviews (RudeService, SlowService, OrderProblem, BadFood, BadNeighborhood, Filthy, MissingFood and Cost) in this case, and they are highly imbalanced (the major 2 classes are 'RudeService' and 'SlowService' and account for 52% of all negative reviews; while the minor classes, 'MissingFood' or 'Cost' for example, account for just around 2% of all negative reviews). In our case, after thorough discussion, we are not leaning to any specific class. Although BadNeighborhood and Cost problems may not be easily solved by the restaurant manager, all other classes are very important from management point of view. So precision and recall are not what we prioritized as our evaluation metrics. We used an accuracy score and a weighted f1 socre as metrics to evaluate models. We used weighted f1 score because we want to take the class imbalance into account, and calculate the metric for each label and find their average weighted by support(number of true predictions for each class label).

### Stemming works better than lemmatization in this review data case:

The way we preprocess the data really has an influence on prediction. The way the corpus is preprocessed will differentiate the results. For example, in this project, we found out that stemming works better than lemmatization while normally lemmatization will do a better job than stemming. This is because we are dealing with Yelp reviews. When writing Yelp reviews, many people do not pay attention to proper grammar rules, some times not even completing words, they don't fully complete their sentances and they are trying to write as simple as possible as long as they can express their dissatisfaction. In this particular case, it makes sense that stemming works better. Thus, in NLP, data scientists shall firstly look into the corpus, understand how the texts look like and then determine which preprocessing steps make sense.

### The classifier model developed in this project can be used for similar fast food restaurant (KFC, Burger King, etc):


## Project presentation link:



