# Python_Supervised_Learning_Challenge
> Utilize knowledge of the imbalanced-learn library and the logistic regression model to compare two datasets

## Overview of the Analysis

For this challenge I will use a dataset containing information on the historical lending activity from a peer-to-peer lending services company to build a supervised machine learning model that can identify the creditworthiness of borrowers. The inherent nature the credit risk problem poses is that of an imbalanced classification problem, ultimatley due to the fact that healthy loans will largely outnumber the unhealthy loans in almost all cases. 

`We will use a couple different techniques described below to train and evaluate models that could potientially solve our problem:`

> Logistic regression Model with original data

Firsty, to determine which loans are healthy (low-risk) or non-healthy (high-risk), I used the data in the loan status column provided by the lending company. Healthy loans are represented by a value of [0] and high-risk ones represented by a value of [1]. Next I will split the data into training and test sets by creating two new variables X and y.

- Features: X = all columns in the dataset, excluding for the target variable. 
- Labels: y = "loan_status" - target variable.

Then check the balance of the labels variable y by using the value_counts() function. This will confirm to me that the two classification varibles have imbalanced values. 

Next we will use the imported train_test_split() function to split the data into X training and testing, and then y training and testing sets. From here, import the logistic regression model from sklearn library and instantiate the model. Next use the fit() function to fit the model to our X_train and y_train datasets. Finally, use the model trained with the x and y training sets to predict our X-test data using the predict() function. 

> Logistic regression Model with resampled training data

To resample the data for this model, first import the RandomOverSampler from the imblearn library and instantiate the oversampled model. Then, fit the original training data to the random_oversampler model using the fit_resample() function on X_train and y_train. Use the value_counts() function again at this point to check and ensure both variables have balanced values. 

Next, use the logistic regression classifier and the resampled data to fit the model using X_oversampled and y_oversampled and make predictions using the predict() function and X_test dataset again. Using y_test and the resampled predictions variable created in the previous step, print out the models balanced accuracy score, confusion matrix, and classification report to review how our model performed.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Based on the precision metric for variable 0 (healthy loan predictions), our model seems to be 100% correct in predicting which loans would be healthy loans and 85% correct in predicting which loans would be high-risk loans; with an overall balanced accuracy score of 95%. 
  * The recall scores are also high, with almost perfect a 100% recall score for variable 0 and above 90% for variable 1. The model scores on these metrics would indicate our model does a good job in predicting the risk level of loans, however, the recall score for high-risk loans could be higher which would result in less false positive predictions.


* Machine Learning Model 2:
  * Based on the metrics derived from the resampled model, the oversampling of the model helped generate an overall balanced accuracy score of 99%, which is an improvment in terms of accuracy, in comparison to accuracy score generated by the original imbalanced model. 
  * The recall metric for variable 1 increased significantly with the use of the oversampled model, increasing from 91% recall to 99%. This increase in recall for variable 1 would mean the model performs better in terms of catching mistakes in the data, and ultimatley resulting in less loans being predicted and classified incorrectly.
  * The precision was almost identical to that of the model with the original data, indicating precision would not be a good metric to compare the two models on.

## Summary

Based on the results of the model, in terms of recall and overall accuracy, the model with the resampled data performed better than the model with the original data, and therefore performed the best out of the two. The recall rates on the resampled model of 99% for both variables is a very strong result, and indicates our model has a very low chance of making mistakes when classifying loans as low-risk or high-risk. It is more important to predict the high-risk [1] loans correctly because you would not want loans misclassified as healthy when they actuallly are not healthy.

My overall prediction after the reviewal of the analysis would be to use the resampled model as a starter model and keep adjusting the model, in terms of features and/or possibly the machine learning library use, to see if the precision and recall could be improved any further. The resampled model had strong performance overall relating to the problem is was designed to solve and can be moved forward with for further development or more trials.
