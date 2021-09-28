# Movie_Correlation_Project


This aim of this project was to practice correlational analysis in python by exploring potential features that are related to improved gross box office earnings for film releases.

Inspiration for this project came from [Alex The Analyst's](https://www.youtube.com/channel/UC7cs8q-gJRlGwj4A8OmCmXg) Youtube channel.

The data used for this project came from the Kaggle [dataset](https://www.kaggle.com/danielgrijalvas/movies/version/2) provided by [Daniel Grijalva](https://www.kaggle.com/danielgrijalvas).

## Project Overview

Having downloaded the data of interest, the data was read into a Jupyter Notebook for analysis, following some minor cleaning and manipulation.

### Actions in Python

First and foremost I explored the shape of the data, any columns with missing values and the included data types were examined. Following this, I used one of my favourite simple pieces of code to examine the unique values in each column.

    for c in df.columns:
       print ("---- %s ---" % c)
       print (df[c].value_counts())

This is a basic for loop that prints out the unique values, and value counts, for each column. Of course, it works best for columns with limited possible values (in this case 'country' or 'genre').

From here, some light data cleaning was required:
- Converting 'gross' and 'budget' to integer data types
- Create a 'release_year' column based on the year of 'released', as the provided year didn't match this

Following this, I began to examine some potential correlations of the data starting with 'budget' and 'gross', plotting on a scatter graph. This showed that was a positive correlation between the production budget and gross earnings of a film, which makes reasonable sense and what most production companies would hope to see.

![scatter](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/scatter%20screenshot.png)

A correlation matrix was then created to show how each feature correlated with eachother, this was using the Pearson correlation method. Of course, wholst this would have included all columns in the dataframe, only the numeric features were shown in the resulting matrix (will come back to this later). We can now clearly see the correlation coefficient of each feature but to aid in readability this matrix was replicated as a heatmap also.

![numericpearson](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/numeric%20pearson.png)
![numericmatrix](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/numeric%20matrix.png)

I then created a list of these numeric attributes (dropping 'year' for my own 'release_year') which would then be looped through to create scatterplots of each feature against gross earnings, again to better visualise the relationship between these features and gross earnings.

![scatterloop1](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/loop%20scatter%201.png)
![scatterloop2](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/loop%20scatter%202.png)
![scatterloop3](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/loop%20scatter%203.png)

> *Both Kendall and Spearman correlation matrices were also created, just as a practice for using different correlation methods.*

I then wrote a loop to convert all object data type fields into a category data type, this meant these could then be encoded allowing us to identify correlation coefficients between all features and gross earnings, not just the inherently numeric fields.

       df4_numeric = df3
        
    df4_numeric.head()
         
    for col in df4_numeric.columns:
        if(df4_numeric[col].dtype == 'object'):
            df4_numeric[col]=df4_numeric[col].astype('category')
            df4_numeric[col] = df4_numeric[col].cat.codes

Once again a heatmap was created to visualise the correlation relationships across the board.

![allmatrix](https://github.com/Dejean97/Movie_Correlation_Project/blob/main/all%20matrix.png)

With the now all numeric feature dataframe, a correlation matrix was made and then unstacked to produce a list of each feature with the respective correlation coefficient against each of the other features. Two lists were then created, all pairs with a correlation coefficient > 0.5 and those < -0.5 to identify all strong posiive, and negative, correlations respectively.

> *It just so happened in this dataset there were no negatively correlated features.*

From this analysis, we can identify that Award Votes and Production Budget had the highest correlation to Gross Earnings. Whereby, in theory, the more financial resources available to a film's production and the more award nominations/votes it received the greater the financial performance produced in box office earnings. However, it's important to note that correlation analysis only identifies the existence of a relationship and not causation, meaning from this we can't identify whether films that get more award votes earn more in the box office or whether earning more in the box office **then** translates into more award votes, as an example.

## Roundup

In summary, this project allowed me to practice some more python and data manipulation in a reasonbly productive way. I was able to practice analysing data to identify features that affect the success, or failure, of another. Whilst this method wasn't particularly scientific, and only examined coefficients as opposed to whether they were significant, it's a decent start and would potentially give direction for future more robust and deep dive analysis.
