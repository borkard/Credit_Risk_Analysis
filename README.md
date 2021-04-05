# Credit_Risk_Analysis

## Overview
This machine learning project used scikit-learn and imbalanced-learn to train and evaluate models to determine credit card risk using a credit card credit dataset from LendingClub, a peer-to-peer lending services company. Six different techniques were used to train and evaluate models with unbalanced classes to determine credit risk: Oversampling with the RandomOverSampler and SMOTE algorithms, Undersampling with the ClusterCentroids algorithm, a combination of over and under sampling with the SMOTEENN algorithm, and two machine learning models that reduce bias - the BalancedRandomForestClassifer and EasyEnsembleClassifier. The following is an analysis of the models and their results.

## Results

### Naive Random Oversampling
The Naive Random Oversampling method used RandomOverSampler to resample the data and enlarge the minority class of training data to use in a logistic regression model. The logistic regression model was trained and the following image and information refers to the resulting balanced accuracy score, confusion matrix, and classification report.

![naive_random_oversampling.PNG](https://github.com/borkard/Credit_Risk_Analysis/blob/main/Images/naive_random_oversampling.PNG)

* The balanced accuracy score for this model is around 62.6%, meaning that the model predicted the credit risk accurately 62.6% of the time. This is a fairly positive score, but not excellent. 
* The precision scores for this model are very skewed toward the low-risk loans as all of the low-risk loans were correctly predicted, but nearly none of the high-risk loans were accurately predicted. This model is not great for identifying high-risk loans.
* The recall scores for this model show that the model is better at identifying positive low-risk loans (0.67) and decent at positively identifying high-risk loans (0.59), but the recall scores are not great for either.


### SMOTE Oversampling
The SMOTE Oversampling method used SMOTE to resample the data and enlarge the minority class of training data to use in a logistic regression model. The logistic regression model was trained and the following image and information refers to the resulting balanced accuracy score, confusion matrix, and classification report.

![SMOTE_oversampling.PNG](https://github.com/borkard/Credit_Risk_Analysis/blob/main/Images/SMOTE_oversampling.PNG)

* The balanced accuracy score for this model is around 63%, meaning that the model predicted the credit risk accurately 63% of the time. This is a fairly positive score, but not excellent. 
* The precision scores for this model are very skewed toward the low-risk loans as all of the low-risk loans were correctly predicted, but nearly none of the high-risk loans were accurately predicted. This model is not great for identifying high-risk loans.
* The recall for both low and high risk loans were around 63%, meaning that the model found all positive instance 63% of the time. This is not a great score when trying to identify high-risk loans.


### Undersampling
The Undersampling method used Cluster Centroids to resample the data and reduce the majority class of training data to use in a logistic regression model. The logistic regression model was trained and the following image and information refers to the resulting balanced accuracy score, confusion matrix, and classification report.

![undersampling.PNG](https://github.com/borkard/Credit_Risk_Analysis/blob/main/Images/undersampling.PNG)

**This code is for a bulleted list**
* The balanced accuracy score for the undersampling technique was around 51%, meaning that only 51% of the testing data was accurately classified. This is not an ideal accuracy score.
* The precision scores for this model are very skewed toward the low-risk loans as all of the low-risk loans were correctly predicted, but nearly none of the high-risk loans were accurately predicted. This model is not great for identifying high-risk loans.
* The recall scores for the high-risk loans were around 0.59 and the recall scores for low-risk loans were around 0.43. While the high-risk recall is much better, both recall scores are low and show that many of the positives were not accurately predicted.


### Combination (Over and Under) Sampling (SMOTEENN)
The Combination method(over and under sampling) used SMOTEENN to remove outliers and resample the data to use in a logistic regression model. The logistic regression model was trained and the following image and information refers to the resulting balanced accuracy score, confusion matrix, and classification report.

![SMOTEENN_combination.PNG](https://github.com/borkard/Credit_Risk_Analysis/blob/main/Images/SMOTEENN_combination.PNG)

**This code is for a bulleted list**
* The balanced accuracy score for the undersampling technique was around 63.8%, meaning that only 63.8% of the testing data was accurately classified. This is a higher accuracy score than many of the other techniques.
* The precision scores for this model are very skewed toward the low-risk loans as all of the low-risk loans were correctly predicted, but nearly none of the high-risk loans were accurately predicted.
* The high-risk recall score for this model is fairly high at 0.70 and the low-risk recall score is average at 0.57. Compared to the previous techniques, this model is much better at identifying true high-risk loans. 


### Balanced Random Forest Classifier
The Balanced Random Forest Classifier was used to create 100 decision trees to classify the testing data.The following image and information refers to the resulting balanced accuracy score, confusion matrix, and classification report.

![balanced_random_forest.PNG](https://github.com/borkard/Credit_Risk_Analysis/blob/main/Images/balanced_random_forest.PNG)

**This code is for a bulleted list**
* The balanced accuracy score for this model is comparatively high at 78.8%, meaning that 78.8% of the testing credit data was accurately classified.
* The precision scores for this model are very skewed toward the low-risk loans as all of the low-risk loans were correctly predicted, but nearly none of the high-risk loans were accurately predicted.
* The recall score for low-risk loans is very high at 0.91 and the recall score for high-risk loans is fairly high at 0.67. This shows that the classifier is good at predicting true positives for low-risk loans.


### Easy Ensemble AdaBoost Classifier
The Easy Ensemble AdaBoost Classifier was used to train and evaluate models to classify the testing data.The following image and information refers to the resulting balanced accuracy score, confusion matrix, and classification report.

![easy_ensemble_classifier.PNG](https://github.com/borkard/Credit_Risk_Analysis/blob/main/Images/easy_ensemble_classifier.PNG)

**This code is for a bulleted list**
* The balanced accuracy score for this model high at around 92.5%, meaning that the classifier accurately predicted the credit risk 92.5% of the time.
* The precision scores for this model are very skewed toward the low-risk loans as all of the low-risk loans were correctly predicted, but few of the high-risk loans were accurately predicted.
* The recall scores for both high and low risk were quite high in this model at 0.91 for high-risk loans and 0.94 for low-risk loans. This shows the high rate of true positives.


## Summary
All of the machine learning models had low precision scores for the high-risk loans in accurately predicting positives. The balanced accuracy score for the models varied with the lowest score for the undersampling method and a high score with the AdaBoost classifier. Recall scores also varied between models with the lowest scores for undersampling and highest with the classifying methods. Of the models created, the Easy Ensemble AdaBoost Classifier would be the best model to use to predict credit risk due to the high recall scores for both high and low risk loans, as well as an accuracy score of 92.5%. The precision for this model is still very off, indicating that the positives are not necessarily accurate, and so this model could be much improved and training and testing more data before putting it into use.
