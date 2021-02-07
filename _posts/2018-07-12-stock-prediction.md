---
layout: post
title:  "Stock Market Prediction Using Machine Learning"
date:   2018-07-07
---

As part of the Machine Learning Special Interest Group Summer Term, we were asked to implement a basic model for Stock
Market Prediction using Supervised Learning concepts. It was a fun project. We were expeced to create a model that predicts the stock trend
of a symbol. Sourcing of data, pre-processing, model selection and other aspects were to be implemented by
us on our own. Seniors were helpful at various stages. 

I decided on implementing the project with SVC on various kernels at first. I sourced data from Quandl. Registered at their website, got the api key, downloaded the data using a python script I wrote. I divided the date into two sets, Training and Dev/Test set. The pre-processing was the really challenging part. Being a very popular project in the Beginners' community, I had a plethora of Github repositories to look into.

It is during this project that I realised the difference between going through the study material and actually
implementing a ML model. Though the data set I procured was quite clean, yet I encountered several problems with
it during Feature Scaling.

I then implemented Ensemble Classifiers. I started with RandomForest Classification. Subsequently, read about Boosting Algorithms, Bagging Algorithms. It was fun. Finally, I implemented AdaBoost and VotingClassifier in order to get the best prediction from the various models.

I look forward to tune this project for greater accuracy. Will train this data with DNNs.

[Take a look!](https://github.com/siddhantkhandelwal/Stock-Market-Prediction-Using-ML)