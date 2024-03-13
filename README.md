# Twitter Bot Detection Using Machine Learning and Explainable AI
## Table of Contents
- [Executive Summary](#executive-summary)
- [Data Overview](#data-overview)
- [Getting Started](#getting-started)
  - [Importing Packages](#importing-packages)
  - [Helper Functions](#helper-functions)
  - [Feature Engineering](#feature-engineering)
  - [Cleaning Tweets](#cleaning-tweets)
  - [Sentiment Analysis](#sentiment-analysis) 
- [EDA](#eda)
- [Methodology](#methodology)
- [Results and Discussion](#results-and-discussion)
- [Conclusion and Impact](#conclusion-and-impact)

## Executive Summary
Bot-generated content on social media platforms has led to an increase in the spread of misinformation and trends being manipulated. The increased frequency of these bot accounts can degrade the user experience which, in turn, can lead to less engagement on the site. The objectives of this analysis are to implement a variety of advanced machine learning methodologies on a Twitter Bot Detection dataset from Kaggle as well as applying explainable AI techniques to help understand the results. By detecting bot-generated content in social media sites like Twitter we can help achieve a safer online space. 

## Data Overview
This dataset is publicly available on Kaggle and was generated using the Faker package in Python. It was created with many beneficial features for bot detection such as tweet, follower_count, verified, mention_count and created_at (timestamp). The dataset contains 50,000 tweets from 40,000 users.  (https://www.kaggle.com/datasets/goyaladi/twitter-bot-detection-dataset?select=bot_detection_data.csv)

## Getting Started
### Importing Packages
Various packages were utilized for this project including shap, lime, nltk, sklearn and tensorflow to name a few. We utilized packages based on the following categories: Data Preprocessing, Feature Engineering, Text Processing, ML Model Building, Neural Network/Deep Learning and Model Evaluation/Explainability. 

### Helper Functions
Many unique helper functions were created to aid in cleaning of tweets, preprocessing tweets, performing LDA on tweets, and getting sentiment scores for a tweet to highlight a few. 

### Feature Engineering
The data provided us with a positive start in terms of features for analysis but we felt creating some ourselves could prove even more beneficial. A few examples of features we engineered: extracted date and time components, used len() function to calculate length of tweets, counted question marks and exclamation points and stored in new column,  calculated the Automated Readability Index of each tweet. 

### Cleaning Tweets
We created two functions, clean_tweet and preprocess_tweet, which clean the tweets in our data and then preprocesses the tweet by tokenizing, removing stopwords and lemmatizing the tokens.

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/51147e4b-0d18-48d1-873a-59252d233cd2)
![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/1b8adc4a-1fbf-4798-aa41-36db054ead91)


### Sentiment Analysis
To accurately assess sentiment, we downloaded the VADER lexicon, a pre-built, finely-tuned list of words and emoticons with their associated sentiment scores. This lexicon is particularly adept at handling the nuances and slang present in social media content. We calculated the compound sentiment score for each tweet and then categorized each score into "Positive", "Negative" and "Neutral." 

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/f19cd080-74da-4e86-9188-7d18bdb7fe56)

## EDA
Our EDA features a wide range of visualizations aimed at providing geographical and demographical insights, temporal analysis, engagement and content analysis, as well as evaluating language complexity and diversity.

Geographical and Demographical Insights:

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/d393f0a7-08fa-433c-a67c-5f144e2ad07d)


Temporal Analysis:

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/0f0afeaa-1b82-44f9-b1e5-35a0e3943e12)


Engagement and Content Analysis:

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/4d4e38b7-eee1-42fb-a47e-b942e823a741)


Language Complexity and Diversity:

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/e32177b4-2f7f-45ec-84fa-fbbd19a74be8)


## Methodology
We wanted to see how a variety of Machine Learning Models fared on our dataset while utilizing our engineered features and sentiment analysis. After running models such as Random Forest Classification, Logistic Regression, Support Vector Machines, K-Nearest Neighbors, Gradient Boosting and a Majority Voting model we weren't satisfied and proceeded on with Neural Networks. We ran a Multilayer Perceptron (MLP), Recurrent Neural Network and Long Short-Term Memory Network (LSTM). After comparing results over all of the models ran we determined that the Recurrent Neural Network (RNN) yielded the best performance in predicting whether an account was a bot, achieving the highest accuracy among all models tested.

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/d5b2c570-5d10-4b3f-b3e2-f689add954ed)


## Results and Discussion
By utilizing LIME and SHAP, we interpreted our results in a more comprehensible manner.. This analysis allowed us to understand which features are most influential in predicting bot behavior as well as breaking down each tweet into what words contributed to its bot or not prediction. (picture of lime breakdown. picture of shap breakdown) We then ran LDA on the human text data and the bot text data to see which words are most associated with each label. We found from utilizing LIME and the LDA that lots of the words in human tweets are experiential with a narrative nature, while words in bot tweets are more informational and target a broader audience. 

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/fd664ff7-c502-484e-8ba3-80995e27e283)

![image](https://github.com/mikemeissner1/twitter_bot_detection_XAI/assets/159487309/a9feecc9-af09-4c9e-a6fe-5f6aa99fc579)


## Conclusion and Impact
Our findings underscore the superior capability of LSTM models over other neural networks and machine learning approaches in detecting language patterns indicative of bots, with notable improvements in accuracy and a variety of other performance metrics. Being able to implement Explainable AI techniques like LIME and SHAP allowed us to be more detailed in our understanding of feature influence, while allowing for more interpretable breakdowns of what words contributed to bot-generated content. The use of these models and Explainable AI techniques can help enable a safer online space for social media users. 
