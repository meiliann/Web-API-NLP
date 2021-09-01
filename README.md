# Project 3: Web APIs & NLP

## Problem Statement
WhatToWatch.com is a new platform for movie and tv shows lovers to share their reviews by posting on the community forum. <br>
Currently, there's no category filter to differentiate the posts in the forum. To improve user experience, the marketing team would like to create two categories in the forum to separate the posts - Netflix posts and AmazonPrimeVideo posts. <br>
This will allow users to read posts based on Netflix and AmazonPrimeVideo respectively as there's feedback that users are more keen to read posts of the platform they are using so they can see what movies or tv shows would same-platform users recommend. <br>

WhatToWatch company has approached Skippy's data science team, which I'm in, to help create and train a classification model that can classify posts into the correct category taking reference from the targeted subreddits - Netflix and AmazonPrimeVideo.<br>

Our team pulled the data via PushShift API and selected 3 classification models to train the models. We will then chose the model with the best accuracy score since the data pulled are of equal classes. <br>

With the best model selected, Skippy's data science team would be able to use it to segregate WhatToWatch.com posts into Netflix and AmazonPrimeVideo respectively and achieve WhatToWatch company's objective. And moving forward, the model will help them to automatically allocate new post to the correct category.<br> 

Our data science team can make use of this modeling to help with other clients' projects that requires classification  since the framework is already there.


### Data collection
- [https://www.reddit.com/r/netflix/](https://www.reddit.com/r/netflix/)
- [https://www.reddit.com/r/AmazonPrimeVideo/](https://www.reddit.com/r/AmazonPrimeVideo/)


### Summary
Using the PushShift API, I managed to pull 1,000 rows of data for each subreddit for my modeling later on. I cleaned the data by removing unnecessary words and punctuations, drop null and duplicate values and also lemmatize based on part of speech (POS) tag to get the root word for the best result.<br><br>
After which, I combine the data and did train-test-split to test out each of the classification model that I have chosen - Logistic regression, Random forest and Multinomial Naive Bayes. For each model, I use GridSearchCV to see whether CountVectorizer and TF-IDF Vectorizer will give a better score. Then, I select the model by chosing the one with the best accuracy score, and also factoring the recall, specificity and precision scores as well.



### Conclusion and recommendations

Based on the results of the 3 models, I would recommend Logistic regression with CountVectorizer to do the classification of Netflix and Amazon Prime Video subreddits which will help with categorising current and future WhatToWatch posts with at least 85% accuracy.  <br>

To increase the accuracy further, I will pull more data and see if the score can be improved. Compared to the baseline accuracy of 50%, Logistic regression is a good model to classify and predict the posts. <br>
I will also consider looking at other reputable sources other than subreddits and use its data as a standalone or combine with the existing subreddits to see if the accuracy score can be improved.<br>

Being part of Skippy data science team, I can use this model to address other clients' classification problems by pulling the data they want to reference to and use Logistic regression with CountVectorizer. The limitation of Logistic regression is that it's limited to two-class classification problems, therefore, if I want to classify more than 2 categories/classes, this model would not be suitable. In that case, I would need to consider using Random forest, Multinomial Naive Bayes or even introduce a new model - Multinomial logistic regression and see which works better for multi-class classification.

 
