
## Credit Risk Analysis 
##                --Using Logistic Regression Model and ROS Method


## Overview and purpose

Credit risk analysis is a process of predicting and assessing the probability of loss when lending money to a borrower. The purpose of this project is to use different machine learning models to conduct risk analysis, compare their performance and select the best one to help a peer-to-peer lending service company identify the creditworthiness of borrowers. The lending dataset provided is split, resampled, and tested. Logistic regression model is implemented and random over sampler (ROS) method is used to optimize the model.


## Results

The lending dataset used here contains information about loan size, interest rate, borrower's income, debt to income ratio and number of accounts etc., to predict if a loan is healthy or high-risk. 

Our analysis steps are as follows: First, the dataset was split into training and testing sets. Second, a logistic regression model from scikit-learn library was trained on the training set and tested on the testing set. Third, due to the observed imbalance in the data, a resampled training set was created using ROS method. Fourth, a new logistic regression model was trained and tested based on the resampled dataset. Finally, the predictions of the two models were compared and evaluated.


##  Machine Learning Model 1: Logistic regression model fit with original dataset

The findings of model 1 are as below:

* The analysis shows that the model 1 has an high balanced accuracy  score of 0.944.
   
According to the below classification report of model 1:

 ![Classification Report-Model 1](https://github.com/wei3chen2/credit-risk-classification/blob/main/Classification%20Report-Model%201.png) 

* The model has high accuracy of 0.99 for both classes.
* The model has a slightly lower precision and recall for class 1 (high risk loan) than for class 0 (healthy loan), which means it has more false positives and false negatives for class 1. And the model has a high f1-score for both classes, which means it has a good balance between precision and recall. 
* The support shows that there are much more instances of majority class 0(75036 healthy loan) than minority class 1(2500 high risk loan), which indicates a class imbalance.

##  Machine Learning Model 2: Logistic regression model fit with resampled dataset

Therefore, due to the imbalanced dataset, we are considering to use ROS method to resample the data and reduce the possible bias towards majority class healthy loan.

* After resampling, we obtain a balanced dataset with equal counts for both classes. 
* The balanced accuracy score is increased to a higher level of 0.995.

 ![Classification Report_Model 2_Resampled Data](https://github.com/wei3chen2/credit-risk-classification/blob/main/Classification%20Report_Model%202_Resampled%20Data.png) 


* The above classification report shows that with resampled data, the new model has a high accuracy of 1.00 in classification for both classes. 
* The model has the same precision for class 1 (0.87) as before, but a higher recall (1.00 vs 0.89), and higher f1-score(0.93 vs 0.88) for class 1, which means it performs better on predicting a high risk loan. 
* The cost of misclassifying a healthy loan as high-risk is lower than the cost of missing a high-risk loan, so this improvement is meaningful.


## Conclusion:


To summarize, this project aims to use machine learning models to predict and compare high-risk and healthy loans based on a lending dataset. Both models perform well in identifying healthy loans, but model 2, the logistic regression model trained on resampled data, has a clear advantage in detecting class “1” high-risk loans. Model 2 has a higher recall score and a higher f1-score for high-risk loan, which means it can correctly classify most of the high-risk instances and reduce the false positives. Moreover, the cost of misclassifying a healthy loan as high-risk is lower than the cost of missing a high-risk loan, so it is more prudent to have a model that can accurately identify high-risk instances.

Therefore, we recommend model 2, the logistic regression model optimized with ROS method, as the best model for this project.





