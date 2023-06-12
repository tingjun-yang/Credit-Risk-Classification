# Credit Risk Classification

## Overview of the Analysis

Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. In this project , I use various techniques to train and evaluate models with imbalanced classes. 

I use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers. The dataset includes the following information:
* loan_size
* interest_rate
* borrower_income
* debt_to_income
* num_of_accounts
* derogatory_marks
* total_debt

The information I am trying to predict is the variable called `loan_status`. A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting. Using the `value_counts` function, I find this variable is very imbalanced, with 75036 of 0 (healthy loan) and 2500 of 1 (high risky of defaulting).

I use a logistic regression model (`LogisticRegression`) to compare two versions of the dataset. First, I use the original dataset. Second, I resample the data by using the RandomOverSampler module from the imbalanced-learn library.
<!--
For both cases, you’ll get the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.


In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
-->

## Results

<!--
Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.
-->

* Machine Learning Model 1:
  * The accuracy score for the testing samples is 0.952. The precision is 1.00 for healthy loans and 0.85 for risky loans. The recall is 0.99 for healthy loans and 0.91 for risky loans. 



* Machine Learning Model 2:
  * The accuracy score for the testing samples is 0.994. The precision is 1.00 for healthy loans and 0.84 for risky loans. The recall is 0.99 for healthy loans and 0.99 for risky loans. 

## Summary

<!--
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
-->

The second machine learning model trained on resampled dataset is recommended as it gives a much higher recall score for the risky loans compared with the first model (0.99 vs 0.91) while the precisions for risky loans are similar (0.84 vs 0.85). It is more important to identify the risky loans in order to avoid financial losses. The second model is able to identify 99% of the high risky loans while the first model is able to identify 91% of the high risky loans. Therefore, the performance of the second model is better. 