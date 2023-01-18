# Business Understanding

## *About Movie*
In this case study, I used a film from the United States called Joker, which was released in 2019 and starred a reasonably well-known actor named Joaquin Phoenix. Of course, some viewers are familiar with the Joker (2019). The awards this film has received speak to this. According to Insider.com, Joker deserves 11 Oscar nominations. This is the most number of films released in 2019[^1].

## *Problem Statement*
Joker (2019) has got a lot of criticism from reviewers despite its success. Rotten Tomatoes gave it a score of 68%, and Metacritic gave it a score of 59 out of 100. This caught our interest, so we decided to do a case study on how sentiment analysis for the film Joker (2019) is based on audience reviews utilizing a support vector machine (SVM) and logistic regression ( LogR).

# Data Understanding

## *Data Retrieval*
The data for this case study was gathered manually using Python for web scraping. I get information from the metacritic website (https://www.metacritic.com/movie/joker/user-reviews).

## *Data Information*
* `Username` : account name shown in the review
* `Review` : content of user-written reviews
* `Rating` : users' ratings of movie satisfaction range from 0 to 10
* `Thumbsup` : number of likes for each review
* `Date` : upload date

# Data Preparation
There are numerous approaches to preparing the data for model construction at this point. These processes are as follows: identifying the suitable attributes for analysis (select data), cleaning data (clean data), constructing new attributes (construct data), integrating data from several sources (integrate data), and reformatting data that is no longer appropriate (format data)[^2]. I just **clean data** and **construct data** because it is in accordance with the needs of the analysis.
```
def transform_rating(rating):
    if rating == 10 or rating == 9 or rating == 8 or rating == 7:
        return "Good"
    if rating == 6 or rating == 5 or rating == 4:
        return "Neutral"
    if rating == 3 or rating == 2 or rating == 1 or rating == 0:
        return "Bad"
```

# Visualization and Exploratory Data Analysis (EDA)
The EDA is performed using bars, histograms, and scatter plots to help preview the data before making any assumptions

# Text Processing
Text processing is the automated method of gaining meaningful insights from text data by analyzing and sorting unstructured data[^3]. Before developing the model, I go through the following processes for text processing.
  * Change all words to lowercase
  * Remove punctuations
  * Remove whitespace
  * Stopword removal
  * Lemmatization
  
# Model Building 
There are two approaches in model construction for sentiment analysis at this stage, including support vector machine (SVM) and logistic regression (LogR). I use scikit learn for modeling and eavluating the results of the modeling.

# Evaluation
I conduct the evaluation using the *classification report*. The findings of the two algorithms that have been carried out. With an accuracy score of 92%, the logistic regression technique outperforms the support vector machine. Aside from that, I performed hyperparameter tuning for both algorithms, however the results were lower, with an accuracy score of 90%.

[^1]: Sarkisian, J. (2020). *Why ‘Joker’ deserves its 11 Oscar nominations*. [online] Insider. Available at: https://www.insider.com [Accessed: 9 Dec. 2022].
[^2]: Data Science Process Alliance. (2018). *What is CRISP DM? - Data Science Process Alliance*. [online] Available at: https://www.datascience-pm.com/crisp-dm-2/ [Accessed: 10 Dec. 2022].
[^3]: MonkeyLearn Blog. (2019). *Text Processing: What Is It?* [online] Tersedia di: https://monkeylearn.com/blog/text-processing/ [Diakses 20 Des. 2022].
