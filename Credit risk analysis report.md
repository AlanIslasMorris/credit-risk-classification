# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Purpose of the analysis:
* The database contains financial information of the potential client. As a loan is being requested, the model should be able to assess the risk based on customer information
* Financial data included: client income, loan requested, interest rate, debt to income ratio, number of accounts, derogatory marks and total debt
* Variable to predict: loan status 
  The model should identify when a borrower is unlikely to be able to pay back. If e.g. the debt to income ratio is high; if the loan requested sums up with previous loan; perhaps if the client has previous derogatory marks or a several accounts... The machine learning model takes into account does concepts and using the trianing set will learn how does variables impact in the loan status. 
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
value_counts: It was used to check if the database is unbalanced e.g. if the model trains with a highly unbalanced database where the majority of the registers are low risk loans, then, the machine learning algorithm would tend to be more precise detecting cases where the loan is secure but it would have a higher degree of false positives in cases where the loan is riske.
* Describe the stages of the machine learning process you went through as part of this analysis.
First the database is loaded, then the db is splitted in two sets: training and testing. The model is defined in this case the logistic regression. The training set is used so that the algorithm can learn in which cases the loan is risky or not. Later on, once the model is trained; it is used to make predictions of the testing set. Those predictions are compared with the correct data from the testing set and the accuracy of the model is assessed with the confusion matrix, the classification report and with the accuracy score.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
fit_resample: allows the dataset to be balanced, in this way the model will have a similar proportion of risky vs non risky loans.
fit: it alows to train the model with the fit data
train_test_split: It is used to create 4 subsets: training set of the data that is related with the variable we want to predict; training set of the variable we want to predict; X_test and Y_test would be splitted with the same logic but the model won´t use it to train and won't encounter this data until performace is assessed.
## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
Accuracy: It is the ratio of the correctly predicted instances to the total instances in the dataset.
            The model correctly predicted the outcome for approximately 99.18% of the cases, which is very high. 
Precision: It is the ratio of correctly predicted positive observations to the total predicted positives.
            When the model predicts the positive class, it's correct about 84.66% of the time. This is a good 
Recall: True positive rate.
            The model correctly identifies approximately 90.95% of all actual instances of the positive class. This is a good recall score, indicating a relatively low rate of false negatives.


Precision: precision score, indicating a relatively low rate of false positives.

Recall: 
* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
Accuracy: The model's accuracy has slightly improved to approximately 99.38% after balancing the dataset.   

Precision: The precision score is approximately 84.13%, which is slightly lower than before. This means that the model has a slightly higher rate of false positives compared to the previous model.

Recall: The recall score has significantly improved to approximately 99.35%. This indicates that the model is now much better at identifying the positive class without missing almost any.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
The one that is balanced; overall accuracy is improved. Despite a little bit of precision is lost, recall improved significantly.
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? ) 
We want to avoid false negatives, this would represent that the money is given and the customer won't be able to pay. On the other hand if one client is lost and he actually was a good client it could represent a good client lost but it won't be as expensive as one client who does not pay back.

If you do not recommend any of the models, please justify your reasoning.
