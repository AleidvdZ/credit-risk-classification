# credit-risk-classification
## Module 20 Challenge  

## Overview of the Analysis

The purpose of the analysis that as completed was to evaluate a model based on loan risk.  A dataset of historical lending activity from lending company was used to build a model to identify if borrowers would likely enter healthy loan agreements or if they would be at risk to default on the loan.  

The data was a csv (lending_data.csv) provided with the starter code.  The data included the following information for each borrower (for a total of 77536 borrowers):  
* the size of the loan
* the interest rate
* the borrower's income
* the debt to income ratio for the borrower
* the number of accounts a borrower has
* the number of derogatory marks on a borrower's credit report
* the borrower's total debt
* the loan status (0 - a healthy loan; 1 - a loan with high risk of default)

The model focused on relating the loan status (as the label) to the other borrower information (as the features) which basically means that the model is to see if it is possible to predict a borrower's likelyhood of entering a healthy loan or a risky loan based on all of the other customer information.

The method of supervised machine learning that was employed was a logistic regression.  Specifically the label (y) and the features were separated (X) and the data was separated into a training pool (75% by default) and a test pool (the remaining 25%).  The model was then instantiated, fit to the training data, which was followed by predictions using the test data.  A confusion matrix was generated to determine the true/false positives and negatives which then was used to output in a classification report for the testing data.  The results from the model are described below.  

## Results  

The classification report showed the following results:  
* The balanced accuracy score was 0.99 or 99% which is a high score for the overall model  
* For the healthy loans (value of 0) the precision was 1.00 (100%) and recall was 0.99 (99%)  
* For the risky loans (value of 1) the precision was 0.85 (85%) and recall was 0.91 (91%)  

## Summary
(this is a copy of the resonse to question in jupyter notebook file)  

From the Challenge description "A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting."

The logistic regression model has an overall accuracy of 0.99 or 99% which appears to be very accurate.

Breaking down the classification report for healthy loans (value of 0) in terms of precision, it appears that 100% of the loans classified as healthy are truly healthy and doing a manual calculation from the confusion matrix it appears that less than 0.3% of the loans classified as healthy are actually at risk of defaulting. For the same token, the recall for the healthy loans is 99% which supports the precision result as it means that the risk of misclassifying a healthy loan as a high risk loan is 1%.

On the flip side when looking at loans that are at high risk for defaulting (value of 1), the precision is 85%. This means that 85% of loans that are truly risky were identified as such but this means that 15% of the loans identified as risky are actually potentially healthy loans (false positives). In terms of recall the model determined that 91% of the loans were correctly predicted as risky but this means that it missed identifying 9% of the loans that should have been identified as risky (false negatives).

The model favors the correct identification of healthy loans and does a good job of predicting loans in that category. It might incorrectly identify a loan as unhealty (risky) even when it might not be. This model would safeguard the lender by having high accuracy on the identification of healthy loans and not incorrectly accepting a risky loan. It could lose potential customers by identifying loans as risky.   

**Based on the balanced accuracy score of 99% and the fact that the model protects the lender with a high precision and recall for the healthy loans, this model should be recommend for use to the lender.**

## Code Source  
Starting code was provided in the assignment  
Solo challenge (A. van der Zel) with no additional support other than attendance in general office hours  
As always a shout out to instructor Ryan Coble and TA Andrew Krieger    
