# Credit Risk Classification Report 

# Overview

Purpose of the Analysis
Machine learning techniques were used to analyze a dataset of historical lending  activity from a peer-to-peer lending services company 
to build a model that can identify the creditworthiness of borrowers.

# Overview of the Analysis
Factors considered in the analysis included data on:

-the size of the loan

-the interest rate

-borrower income

-debt-to-income ratio

-the number of accounts the borrower held

-derogatory marks against the borrower

-the total debt

The dataset (~77,500 data points) was split into training and testing sets. The training set was used to build Logistic Regression Model 1 using the LogisticRegression from scikit-learn. Logistic Regression Model 1 was then applied to the testing dataset. The purpose of the model was to determine whether a loan to the borrower in the testing set would be low- or high-risk and results are summarized below.
To resample the training data and ensure that the logistic regression model had an equal number of data points to draw from, the training set data was resampled with the RandomOverSampler module from imbalanced-learn. This generated 56,277 data points for both low-risk (0) and high-risk (1) loans, based on the original dataset.
The resampled data was used to build a new logistic regression model (Logistic Regression Model 2). The purpose of Logistic Regression Model 2 was to determine whether a loan to the borrower in the testing set would be low- or high-risk. The results are summarized below.

# Results

loan_status value counts: 
75,036 low risk
2,500 high risk

Logistic Regression Model 1:

Precision: 93% (in predicting low-risk loans, the model was 100% precise, though the model was only 87% precise in predicting high-risk loans)
Accuracy: 94%
Recall: 95% (the model had 100% recall in predicting low-risk loans, but 89% recall in predicting high-risk loans)

Logistic Regression Model 2:

Precision: 93% (predicting low-risk loans, the model was 100% precise, though the model was only 87% precise in predicting high-risk loans)
Accuracy: 100%
Recall: 100%

# Summary
Logistic Regression Model 2 is less likely to predict false negative results. 
However, based on the confusion matrices for each model, Logistic Regression Model 2 predicted slightly more false positives (low-risk when the actual was high-risk).

If the goal of the model is to determine the likelihood of high-risk loans, neither model scores above 90% precision. Logistic Regression Model 2 had fewer false predictions of the testing data overall and would be the best model to use based on the high accuracy and recall of this model.
