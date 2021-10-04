# Machine Learning Trading Bot
Machine Learning Trading Bot

## Summary
* Smaller training period for models works better because it prevents overfitting
* The most accurate model are not the best because they cannot predict negative returns and may have worked better in the test period but may not work in future when other events are encountered.
* Adaboost appears to work better than SVM because it is able to predict the negative returns better than SVM.
* 

## Baseline Analysis
### SVM short is 4 and long is 100.
* The model has an accuracy of 0.55. 
* The strategy returns predicted follow the actual returns till late 2018
and then they deviate from the actual returns. The returns from this model exceed actual returns towards the end of the test period.
* It did a great job with predicting positive returns but not so much with negative returns

![SVM short=4 long=100 Classification Report](Resources/SVM_short_4_long_100_baseline_classification_report.png)

![SVM short=4 long=100](Resources/SVM_short_4_long_100_baseline.png)
![SVM short=4 long=100 Shifted](Resources/SVM_short_4_long_100_baseline_shifted.png)

### AdaBoost short is 4 and long is 100.
* This model also has an overall accuracy of .55 (same as the SVM baseline mode)
* This model does a better job of predicting negative returns than SVM baseline model but at a slight expense of predicting the positive returns.
* The prediced strategy retuns follow the general actual returns trend but deviate from actual return from
late 2017 to early 2020. The returns from this model are almost the same as the actual returns towards the end of the test period.

![AdaBoost short=4 long=100 Classification Report](Resources/Adaboost_short_4_long_100_baseline_classification_report.png)

![AdaBoost short=4 long=100](Resources/Adaboost_short_4_long_100_baseline.png)
![AdaBoost short=4 long=100 Shifted](Resources/Adaboost_short_4_long_100_baseline_shifted.png)

## Change Training Time period 4, 2015 to end of 3, 2017
* Changed the training period to 2 years. Increasing the training period helped increase the accuracy of the SVM model because of overfitting for the positve returns.
* SVM accuracy improved but its ability to predict negative returns was negligible. So This model can be rejected. A dump model predicting 1 always would have performed that same as this model.
* Adaboost model 
### SVM short is 4 and long is 100
* This model suffer from lack of predictive power related to negative returns.
* This model has an overall accuracy of .56. This is better than the baseline models but this is due to increased predictive power for positive returns and comes at an expensive of predicting negative returns.
* This model follows the actual returns till early 2020 and suffers when the downturn happens and starts deviating from the actual returns. This is due to lack of predictive power for negative returns

![SVM short=4 long=100 train 4,2015 to 3,2017 Classification Report](Resources/SVM_short_4_long_100_train_4_2015_3_2017_classification_report.png)

![SVM short=4 long=100 train 4,2015 to 3,2017](Resources/SVM_short_4_long_100_train_4_2015_3_2017.png)
![SVM short=4 long=100 train 4,2015 to 3,2017 Shifted](Resources/SVM_short_4_long_100_train_4_2015_3_2017_shifted.png)

### Adaboost short is 4 and long is 100
* This model has an overall accuracy of .50. This is worse than all the previous models including baseline models.
* This model has a good balance of predictive power of postive returns and negative returns.
* This model deviates from actual returns during the pandemic crash and towards the end of test period has 
an opposite direction to the actual returns. This model can be rejected for this reason.
![AdaBoost short=4 long=100 train 4,2015 to 3,2017 Classification Report](Resources/Adaboost_short_4_long_100_train_4_2015_3_2017_classification_report.png)

![AdaBoost short=4 long=100 train 4,2015 to 3,2017](Resources/Adaboost_short_4_long_100_train_4_2015_3_2017.png)
![AdaBoost short=4 long=100 train 4,2015 to 3,2017 Shifted](Resources/Adaboost_short_4_long_100_train_4_2015_3_2017_shifted.png)

## Change Long to 50 from 100 and train period is 4, 2015 to early 4, 2017
### SVM short is 4 and long is 50

![SVM short=4 long=50 train 4,2015 to 4,2017 Classification Report](Resources/SVM_short_4_long_50_train_4_2015_4_2017_classification_report.png)

![SVM short=4 long=50 train 4,2015 to 4,2017](Resources/SVM_short_4_long_50_train_4_2015_4_2017.png)
![SVM short=4 long=50 train 4,2015 to 4,2017 Shifted](Resources/SVM_short_4_long_50_train_4_2015_4_2017_shifted.png)

### Adaboost short is 4 and long is 50
![AdaBoost short=4 long=50 train 4,2015 to 4,2017 Classification Report](Resources/Adaboost_short_4_long_50_train_4_2015_4_2017_classification_report.png)

![AdaBoost short=4 long=50 train 4,2015 to 4,2017](Resources/Adaboost_short_4_long_50_train_4_2015_4_2017.png)
![AdaBoost short=4 long=50 train 4,2015 to 4,2017 Shifted](Resources/Adaboost_short_4_long_50_train_4_2015_4_2017_shifted.png)

## Test runs 
Various iterations of testing was done and the results are as follows:

![Test Results 1](Resources/test_results_various_runs_1.png)
![Test Results 2](Resources/test_results_various_runs_2.png)

Some of the models with the best SVM accuracy started the training period 18 or 6 or 12 months from the initial training data.

If we review the classification report for start after 18 months for 31 month with a short window of 37 and long window of 290, we observe 
![SVM short 37 long 290 start 18 period 31](Resources/SVM_short_37_long_290_start_18_period_31_classification_report.png)
![Adaboost short 37 long 290 start 18 period 31](Resources/Adaboost_short_37_long_290_start_18_period_31_classification_report.png)

If we review the classification report for start after 6 months for 7 month with a short window of 29 and long window of 50, we observe 
![SVM short 29 long 50 start 6 period 7](Resources/SVM_short_29_long_50_start_6_period_7_classification_report.png)
![Adaboost short 29 long 50 start 6 period 7](Resources/Adaboost_short_29_long_50_start_6_period_7_classification_report.png)
