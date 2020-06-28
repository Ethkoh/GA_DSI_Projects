# Project 5: DJI Price Direction Prediction though Natural Language Processing
   ---
  *By Ethan Koh, 29 June 2020*

## Background
The goal of almost every professional or casual financial investor is to better predict stock market prices and reap positive gains. Founded in 1885, the Dow Jones Industrial Average (DJIA) is a stock market index that measures the stock performance of 30 large companies listed on stock exchanges in the United States. It consisted of companies such as 3M, Apple Inc, etc.

Many factors can affect stock prices, ranging from economic landscape, companies acquisitions, to political instability etc. It is almost impossible to pin point specific features that contribute to stock prices movement. This project is not simply about predicting the stock market movement, but also to understand how everyday news might contribute to stock prices movement, if any.


## Problem Statement
Have you thought of putting some savings into the stock market thinking it's sufficient to watch everyday world news to roughly know the stock prices movement? Using the top 25 up voted world news title from Reddit users under the subreddit r/worldnews, we are going to explore and build a model in predicting whether Dow Jones Index(DJI) will increase,decrease or remain the same for a given day. We are having a binary classification as our target variable where DJI labels "1" if the price increase or stays the same, and "0" when the price decreases from the previous trading day. We will be using accuracy as our scoring metric.

## Dataset
Dataset is obtained from Kaggle provided by Sun. The first column is "Date", the second is "Label", and the following ones are news headlines ranging from "Top1" to "Top25". News titles are scrapped from reddit.

Source: Sun, J. (2016, August). Daily News for Stock Market Prediction, Version 1. Retrieved [31 May 2020] from https://www.kaggle.com/aaron7sun/stocknews.

## Executive Summary
Using top 25 world news title from reddit alone may not be a sufficient corpus to train a good model for predicting whether price will go up or down for DJIA. The test score is worse than the baseline model(score:0.5424) despite running a few models and vectorizers. The best model, though below baseline model, was using 3 ngram CountVectorizer with Logisitic Regression with validation accuracy score of 0.5150. Best training Accuracy score during GridSearch was 0.6253. However, cross validation mean score is 0.5153. Overall there is still underfit since validation score is not better than baseline and training score.

Sentimental Analysis using TextBlob was then used to give sentiment scores to the news to model instead of relying on just vectorizing tools from Natural Language Processing. However, the score was still poor below baseline model. Looking into the sentimental score EDA suggest many were give neutral sentiment of score 0, unable to facilitate in modeling.

Though the classification model was not successful, a glimpse into the EDA suggests that everyday news might have little to contribute to the DJIA pricing movement. Hence, this project concludes that watching daily everyday news alone might not be sufficient to decide whether prices are trending upwards or downwards at any given day. Thus, more precaution and work have to be done while trading in stock market. One should not simply trade based on watching daily world news.

## Content
- Import Libraries
- Load CSV
- Macro Analysis
- Split data into training and testing sets
- Baseline Model
- Preprocessing
- Exploratory Data Analysis
- Fit Logistic Model with CountVectorizer 1-gram
- Fit Logistic Model with CountVectorizer 2-gram
- Fit Logistic Model with CountVectorizer 3-gram
- Fit Logistic Model with Tfidf Vectorizer 2-gram
- Fit Random Forest with CountVectorizer 2-gram
- Fit Random Forest with Tfidf Vectorizer
- Fit Naive Bayes with CountVectorizer 2-gram
- Sentimental Score Feature Engineering
- Fit Logistic Regression for the Sentiment Score
- Best Model:  Logistic Regression with CountVectorizer 3-gram
- Conclusion
- Limitations and Recommendation