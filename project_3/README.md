# Project 3: Reddit Natural Language Processing Classification
   ---
  *By Ethan Koh, 18 May 2020*

## Overview
Reddit <sup>1</sup> is a social news collection and discussion site founded in 2005 by two college friends: Steve Huffman and Alexis Ohanian. It has evolved to a home site for many growing communities, also know as subreddits. Within each subreddits, the registered member can create a post and share content such as text stories, links, images, and videos. The rest of the community can comment on posts as a means of discussion. Comments & posts can be upvoted or downvoted like a ranking. The most interesting content rises to the top. There is a large number of subreddits community that surrounds almost any topic of interest you can think of and find like-minded folks. It has been a place for people to seek advice, comfort, share knowledge or humour, and many more.

### Reddit Statistics:
*As of December 4, 2019*
- Average monthly active users: More than 430 Million
- Active communities: More than 130 Thousand
- Average screenviews per month: 21 Billion
- Most visited site in US (on Alexa): 5th

## Problem Set
Given a post, able to classify correctly whether it belongs to Parenting or CasualConversation subreddit. This is a binary classification problem. We will later label Parenting as 1 and CasualConversation as 0

## Dataset
Dataset (from part1 notebook:Project_3_Reddit_API_to_CSV_Part_1.ipynb) is retrieved from r/CasualConversation <sup>2</sup> and r/Parenting <sup>3</sup> subreddits using the Reddit API on 14 May 2020.

## Content:
- Part 1: Project_3_Reddit_API_to_CSV_Part_1.ipynb
- Part 2: Project_3_Reddit_NLP_Classification_Part_2

### Part 2 Contents:
- [Import Libraries](#Import-Libraries)
- [Load Dataset from CSV](#Load-Dataset-from-CSV)
- [Macro Analysis](#Macro-Analysis)
- [Data Cleaning](#Data-Cleaning)<ul>
- [Remove Null values](#Remove-Null-values)
- [Remove Duplicates](#Remove-Duplicates)</ul>
- [Choose stopwords library to use](#Choose-stopwords-library-to-use)<ul>
- [Number of words in total for each subreddit preprocessing](#Number-of-words-in-total-for-each-subreddit-preprocessing)
- [Calculate and Plot Word Frequency](#Calculate-and-Plot-Word-Frequency)
- [Create final stopwords](#Create-final-stopwords)</ul>
- [Combine into `X` and `y`](#Combine-into-X-and-y)
- [Split data into training and testing sets](#Split-data-into-training-and-testing-sets)
- [Words Preprocessing](#Words-Preprocessing)
- [Turn text into features](#Turn-text-into-features)
- [Baseline accuracy](#Baseline-accuracy)
- [Fit a Naive Bayes model](#Fit-a-Naive-Bayes-model)
- [Fit a Logistic Regression model](#Fit-a-Logistic-Regression-model)
- [Fit Random Forest Classifier](#Fit-Random-Forest-Classifier)
- [Combine a few models and get best score](#Combine-a-few-models-and-get-best-score)
- [Fine tuning Logistic Regression hyperparameters](#Fine-tuning-Logistic-Regression-hyperparameters)
- [Fit Final Logistic Model](#Fit-Final-Logistic-Model)
- [Conclusion](#Conclusion)
- [Limitations and Recommendation](#Limitations-and-Recommendation)
- [Sources](#Sources)