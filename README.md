# Python_Supervised_Learning_Challenge
> Utilize knowledge of the imbalanced-learn library and the logistic regression model to compare two datasets

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

For this challenge we will use a dataset containing information on the historical lending activity from a peer-to-peer lending services company to build a supervised machine learning model that can identify the creditworthiness of borrowers. The inherent nature the credit risk problem poses is that of an imbalanced classification problem, ultimatley due to the fact that healthy loans will largely outnumber the unhealthy loans in almost all cases. 

We will use a couple different techniques described below to train and evaluate models that could potientially solve our problem:

> Logistic regression Model with original data

Firsty, to determine which loans are healthy (low-risk) or non-healthy (high-risk), we used the data in the loan status column provided by the lending company. Healthy loans are represented by a value of [0] and high-risk ones represented by a value of [1]. Next we split the data into training and test sets by creating two new variables X and y.

Features: X = all columns in the dataset, excluding for the target variable. 
Labels: y = "loan_status" - target variable.

We then check the balance of the labels variable y by using the value_counts() function. This will confirm to us that our two classification varibles have imbalanced values. 

Next we will use the imported train_test_split() function to split the data into X training and testing, and then y training and testing sets. From here we import the logistic regression model from sklearn library and instantiate the model. Next we use the fit() function to fit the model to our X_train and y_train datasets. Finally, we use the model trained with the x and y training sets to predict our X-test data using the predict() function. 

Using y_test and the predictions variable we created in the previous step, we print out the models balanced accuracy score, confusion matrix, and classification report to review how our model performed. Based on the precision metric for variable 0 (healthy loan predictions), our model seems to be 100% correct in predicting which loans would be healthy loans and 85% correct in predicting which loans would be high-risk loans; with an overall balanced accuracy score of 95%. The recall scores are also high, with almost perfect a 100% recall score for variable 0 and above 90% for variable 1. The model scores on these metrics would indicate our model does a good job in predicting the risk level of loans, however, the recall score for high-risk loans could be higher which would result in less false positive predictions.




* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
