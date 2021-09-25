# Movie_Correlation_Project


This aim of this project was to practice correlational analysis in python by exploring potential features that are related to improved gross box office earnings for film releases.

Inspiration for this project came from [Alex The Analyst's](https://www.youtube.com/channel/UC7cs8q-gJRlGwj4A8OmCmXg) Youtube channel.

The data used for this project came from the Kaggle [dataset](https://www.kaggle.com/danielgrijalvas/movies/version/2) provided by [Daniel Grijalva](https://www.kaggle.com/danielgrijalvas).

## Project Overview

Having downloaded the data of interest, the data was read into a Jupyter Notebook for analysis, following some minor cleaning and manipulation.

### Actions in Python

First and foremost the shape of the data and the included data types were examined. Following this, I used one of my favourite simple pieces of code to examine the unique values in each column.

    for c in df.columns:
       print ("---- %s ---" % c)
       print (df[c].value_counts())

This is a basic for loop that prints out the unique values, and value counts, for each column.

## Roundup

T
