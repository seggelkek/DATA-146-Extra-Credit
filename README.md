# Extra Credit Data 146

In general, this data describes different demographic features of Liberia, allowing one to see how these socioeconomic factors interrelate. Specifically, I analyzed how different regression techniques could be used to predict education status.  

## Data Overview

In addition to the target statistic of education, this data also includes information on location, size, wealth, gender, and age. The histogram below gives a general overview of these variables as well as their spread.

HISTOGRAM

To begin the analysis, I looked into the relationships between each of these variables in order to ensure that there were no compounding relationships between the variables. In this data set, as seen in the heat map, there were no major linear correlations between any individual variables. In many ways this is positive, showing that each demographic feature is contributing its own piece of the puzzle and is not just another way of measuring the same features. The pair plot is also provided below and does give some hope that with scaling and the use of various regressions, a possible model could connect some of these covariates.

HEAT MAP

PAIR PLOT

## Logistic Regression:

TABLE

Overall, the logistic regressions that I tested did not produce models that I would be confident using to predict education status based on other demographic features. The normalized data produced the most accurate model with a R2 score of .64652; however, even this value is not high enough to be satisfied that this was the best model. Nevertheless, these results do demonstrate that applying different scalers can be a powerful tool; simply applying the normalizer scaler increased the accuracy by over 7%.

## kNN:

TABLE

In order to further investigate possible models, I ran a kNN regression with each of the different scalers on the data. As a result of this analysis, the best kNN model that I found was applying the MinMax scaler and assuming that each point had 26 closest neighbors. This regression yielded an average R2 score of .71146.

## Decision Tree:

TABLE

In order to further investigate possible models, I ran decision tree regressions with each of the different scalers on the data. As a result of this analysis, the best decision tree models that I found were on the raw data, applying the normalizer scaler, or applying MinMax scaler and using the parameters of max_depth=9 and min_samples_split=8. These regressions all yielded an average R2 score of .72019.


