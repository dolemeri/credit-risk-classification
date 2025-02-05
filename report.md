# Module 20 Report 

## Overview of the Analysis

The purpose of this analysis was to create a supervised machine learning model that would predict if a loan is healthy or high-risk. The data used was a 77,536 line csv file that contained columns of various data about the loan (amount and interest rate) and the borrower's income, debt and accounts, as well as a column classifying the loan as healthy or high-risk. Only 2,500 of the total loans were classified as high-risk.

To preform the machine learning process the data was:

1. Split into labels and features, with the loan status (healthy or high-risk) being the label and the remaining seven columns as features.
2. The data was then split into training and testing data sets.
3. A Logistic Regression model from sklearn was created with the Limited-memory BFGS ('lbfgs') solver.
   - Logistic Regression was chosen as we are classifying loans as healthy OR high-risk and only those two options.
4. The model was then fit with the training data.
5. Predictions were made with the test data
6. The model was evaluated by comparing the predictions with the test labels.

## Results

Accuracy: **0.992468**

- Balanced Accuracy: **0.96799**
- Precision
  - Healthy: **1.00**
  - High-Risk: **0.84**
- Recall
  - Healthy: **0.99**
  - High-Risk: **0.94**

## Summary


The Logistic Regression model does a very good job predicting healthy loans. However, according to the test data, it classifies 10% of high-risk loans as healthy. While none of the loans used for training are for very large amounts of money (all are less than 24,000), a loan that defaults, especially early in its term, could cost the company more than the interest earned from many healthy loans.

There are also very few high-risk loans for the model to learn from when compared to the number of healthy loans in the data set. If more of these types of loans could be added to the data to train from, there may be improvement to the model.

For trying to classify loans, trying to prevent high-risk loans is more important than giving out a loan as more money can be lost from a single loan that defaults than the interest earned from a loan.
