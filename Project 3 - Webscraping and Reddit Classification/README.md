# Project 3: Webscraping and Reddit Classification

#### Author: Teo Zhan Rui

This project comprises 2 notebooks,
1) main.ipynb : All analysis and findings are found here.
2) supplementary-scrape.ipynb : Code for webscraping pipeline

## Problem Statement

This project involves building a classification model to differentiate between Disney Plus and Netflix posts on Reddit. It is then possible for future use in classifying posts that may be scraped from other social media platforms or other related subreddits. These posts may not be explicitedly labelled as a Disney Plus or Netflix related text. 
In the context of Singapore, Netflix has been the incumbent player as the more popular content subscription service.  Disney Plus was launched recently in March 2021 with some of their crowd pullers already well received in the global markets. 
In addition to classification, I will attempt to use natural language processing techniques to discover topics discussed by the Reddit community and follow up with some recommendation for DisneyPlus to gain market share.

1. What are the commonly discussed DisneyPlus titles? <br>
2. What are the commonly discussed Netflix titles? <br>
3. What are the negative issues discussed among DisneyPlus subscribers? <br>

## Executive Summary

**Key Findings and Recommendations**
1) Many popular DisneyPlus titles, old and new, are the source of discussion among users which turned out to be top predictors in the classifier. 

- WandaVision
- Raya
- Frozen
- Muppets

2) Netflix produces a very range wide of content which may be the reason why the discussions are not centred about several titles. 

- Stranger Things
- Crime Scene: The Vanishing at the Cecil Hotel
- Legends of Korra

3) Technical issues such as device compatibility, playback and customer service must be addressed in order to reduce customer attrition. 

**Machine Learning Model** <br>
The final production uses Logistic Regression with an accuracy score of 100.0% on the training set and 82.3% on the hold out set (X_test). 

#### my data dictionary

|Feature|Type|Description|
|---|---|---|
|subreddit|object|DisneyPlus or Netflix|
|post|object|concatenated text from 'title' and 'selftext' from webscraping|
|processed text|object|lemmatized text with stop words removed|
|num_words|int|number of words in post|
|polarity|float|polarity calculated using textblob|
|label|int|target label, '1' for DisneyPlus, '0' for Netflix|

#### Conclusions
1. Many popular DisneyPlus titles, old and new, are the source of discussion among users which turned out to be top predictors in the classifier. In contrast, the individual titles do not stand out as top predictors for Netflix posts. <br>
2. Netflix produces a very range wide of content which may be the reason why the discussions are not centred about several titles. DisneyPlus can consider expanding beyond the crowd favourites in order to compete. <br>
3. From n-gram exploration data analysis among topic model, technical issues such as device compatibility, playback and customer service are surfaced and must be addressed in order to reduce customer attrition. <br> 

**Suggestion for Further Analysis**
1. Refine unsupervised topic modeling on both subreddits to uncover more topics. <br>
2. Compare existing content catalogue with top positive predictor words from trained model to find more discussed titles among viewers. <br>
3. Fine tune trained Naive Bayes model by removing more words commmon to both subreddit classes. <br>



