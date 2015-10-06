---
layout: post
title: Enter the Bacon
---
![enter](https://myrambling20s.files.wordpress.com/2014/09/adaxr8obgt8cz0d5hp4uuzgibrw.jpg)
***[Enter the Void - this has nothing to do with anything, but it's an awesome movie](http://www.imdb.com/title/tt1191111/)***


**Scenario:**

Kevin Bacon wants to back up his nudity argument with data. The basic premise is - the more male nudity the better. For details please see below. 
[Bacon on Male Nudity](https://www.youtube.com/watch?v=3Dt3IrdampY)


This is a journal of Bacon's efforts. 

**Analysis In Progress**


Nudity Analysis: Median Gross for all genres in dataset
![median_all_genres](images/Median_Gross.png)

Does not seem to mean much here. 

Nudity Analysis: Median Gross for comedies in dataset
![median_all_genres](images/Median_Gross_Comedy.png)

Looks to be a relationship here!

Let's take a look at the spread

![median_all_genres](images/Comedy_Scatter.png)

Let's see how a forecast looks:
![median_all_genres](images/Nudity_Forecast.png)

mehhh not grea. But maybe this can be a helpful feature on top of others. 

Key forecaster 1: Budget

![median_all_genres](images/Budget_Forecast.png)

Key forecaster 2: Quality (Metacritic Score)

![median_all_genres](images/Metacritic_Forecast.png)


Once we feed these features into a best fit model we find out the following:

- metacritic/budget training score 0.434422310815

- nudity level added score **0.473791747823**

- metacritic/budget test score **0.267712588339** 

- nudity level added test score 0.264120598801

This means that while nudity score seemed to help increase fit in the training set it actually reduced the model's ability to forecast gross in the test set. 

**Next Step**

Though the level of nudity (as measured by instances of tagged keywords associated with nudity on IMDB) does not seem to be a useful predicter of gross 

 


 
    