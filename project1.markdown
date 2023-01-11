# Report: Predict Bike Sharing Demand with AutoGluon Solution

## Initial Training

### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

Answer: I decided to round negative count values and the numbers in
count to 0

### What was the top ranked model that performed?

Answer: Top ranked model WeightedEnsemble_L3 with hyper parameter
optimized

## Exploratory data analysis and feature creation

### What did the exploratory analysis find and how did you add additional features?

Answer: Time series analysis showed that:

-   The last 10 days of the month have missing data. i.e. starting on
    the 20^th^;
-   The variations in demand at each hour of the week and on weekends.

Based on the correlation graph, there is a high correlation between the
"month" and seasonality", therefore I removed the seasonality from data.

I decided to categorize some of the continues variables: wind, temp,
humidity, and etc.

### How much better did your model preform after adding additional features and why do you think that is?

Answer: Approximately 26%. If we add significant variables to our model,
performance of our model'll increase.

## Hyper parameter tuning

### How much better did your model preform after trying different hyper parameters?

Answer: Modestly

### If you were given more time with this dataset, where do you think you would spend more time?

Answer: Data preprocessing, feature engineering and hyper parameter
tuning.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.

  model          hpo1                                                 hpo2                              hpo3                  score
  -------------- ---------------------------------------------------- --------------------------------- --------------------- -------
  initial        def                                                  def                               def                   1.39
  add_features   def                                                  def                               def                   0.58
  hpo            CAT(iterations),RF(n_estimators), XT(n_estimators)   GB(num_boost_round, num_leaves)   scheduler, searcher   0.56

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![](vertopal_aa12879fcd254da4a1e9e41b6b370c2d/media/image1.png){width="4.635416666666667in"
height="3.4765627734033244in"}

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

Test_score

![](vertopal_aa12879fcd254da4a1e9e41b6b370c2d/media/image2.png){width="5.0in"
height="3.75in"}

## Summary

Steps:

-   I obtained the data from the "Bike Sharing Demand" kaggle
    competition and opened the csv file via pandas library.

-   Did data preprocessing and feature engineering; analyzed the data by
    using matplotlib library.

-   Built the model using Autogluon. To start with, I built model
    without doing data preprocessing. Later, I added new features and
    did hyperparameter tuning.

-   Sumbitted the csv file to my Kaggle profile.
