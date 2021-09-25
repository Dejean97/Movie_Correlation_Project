# Movie_Correlation_Project


This aim of this project was to practice correlational analysis in python by exploring potential features that are related to improved gross box office earnings for film releases.

Inspiration for this project came from [Alex The Analyst's](https://www.youtube.com/channel/UC7cs8q-gJRlGwj4A8OmCmXg) Youtube channel.

The data used for this project came from the Kaggle [dataset](https://www.kaggle.com/danielgrijalvas/movies/version/2) provided by [Daniel Grijalva](https://www.kaggle.com/danielgrijalvas).

## Project Overview

Having downloaded the data of interest, the data was read into a Jupyter Notebook for analysis, following some minor cleaning and manipulation.

### Actions in Python

First and foremost the shape of the data, any columns with missing values and the included data types were examined. Following this, I used one of my favourite simple pieces of code to examine the unique values in each column.

    for c in df.columns:
       print ("---- %s ---" % c)
       print (df[c].value_counts())

This is a basic for loop that prints out the unique values, and value counts, for each column. Of course, it works best for columns with limited possible values (in this case 'country' or 'genre').

From here, some light data cleaning was required:
- Converting 'gross' and 'budget' to integer data types
- Create a 'release_year' column based on the year of 'released', as the provided year didn't match this

Following this, I began to examine some potential correlations of the data starting with 'budget' and 'gross', plotting on a scatter graph.

![scatter](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/scatter%20screenshot.png)

T
heatmap

![numericpearson](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/numeric%20pearson.png)
![numericmatrix](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/numeric%20matrix.png)

T

![scatterloop1](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/loop%20scatter%201.png)
![scatterloop2](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/loop%20scatter%202.png)
![scatterloop3](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/loop%20scatter%203.png)

Both Kendall and Spearman correlation matrices were also created, just as a practice for using different correlation methods.

From this analysis, we can identify that Award Votes and Production Budget had highest correlation to Gross Earnings.

## Roundup

T
