# Module 20 Report Template

## Overview of the Analysis

In this challenge, I used Logistic Regressor for prediction on loan data.

* Explain the purpose of the analysis.

The purpose of this challenge was to implement our knowledge of python coding, machine learning, and statistical metrics to predict and evaluate predictions on risk level of money lending to customers.

* Explain what financial information the data was on, and what you needed to predict.

There were several different columsn of data, including 'loan_size', 'interest_rate', 'borrower_income', 'debt_to_income', 'num_of_accounts', 'derogatory_marks', 'total_debt', 'loan_status'. I used the last column as the output of my prediction and the rest of the columns were used as features in doing the prediction.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

The values to predict were for risk level of money lending (y = loan_status). This column only contains 0s and 1s which are representing low or high risk of borrower. The column was checked for null values as well as the data type. There were no missing values and all the data in this column was Int64. Value count of this column was 75036 low risk (0) and 2500 high risk (1).

* Describe the stages of the machine learning process you went through as part of this analysis.

For machine learning, the following steps were taken:
    1. necessary libraries were loaded: LogisticRegression, train_test_split, confusion_matrix, classification_report
    2. dataset was read from the local directory as a csv file
    3. dataset was checked for missing values using 'info()' method
    4. dataset was broken down into features and output sets, represented by X and y
    5. dataset was splitted for training and testing prior to prediction (different split_size were used: 0.2, 0.25, 0.3)
    6. Logistic Model was called and fitted on the training dataset
    7. prediction was done and the predicted values along with the test values (y_pred, y_test) were recorded in a DataFrame
    8. confusion matrix (cm) was generated to evaluate model performance
    9. classification report (cr) was generated to evaluate model performance

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).

For the purpose of this challenge, only LogisticRegression was used. However, different split_size values were tested and it was found that having a split ratio of 0.3 achieves the best results, especially for High Risk loans. Since the values of Low Risk loans were constantly 1, there was no performance difference on this part.

## Results

* Machine Learning Model 1:
    * a high model accuracy of 99% was achieved over different split sizes of 0.2, 0.25, and 0.3
    * for Low Risk loans: precision = 1, recall = 1, F1-score = 1
    * for High Risk loans: precision = 0.87, recall = 0.91, F1-score = .89
    * model is performing better on Low Risk loans compared to High Risk. Due to size of Low and High Risk loans, model performance is dominated by Low Risk loans, as a result, accuracy is exceptionally high

## Summary

Since only one model was used, the summary and recommendations are limited to LogisticRegression.
    1. a dataset containing results of a financial institute was used to predict on risk level of lending money to borrowers. 
    2. the dataset was checked and there was no need for data wrangling and any type of preprocessing
    3. it was observed that when LogisticRegression was used, the accuracy of model was constantly at 99%. this shows minimal need to adjust the model
    4. all the Low Risk loans were predicted perfectly
    5. High Risk loan prediction was not as perfect as Low Risk ones but it was in an acceptable range
    6. looking at the size of High and Low Risk loan prediction metrics, it is obvious that there is an imbalance in data analysis which suggests more research is needed to implement a model capable of   handling this imbalance.
    7. looking at confusion matrix values, we can see that there are 66 Low Risk values predicted as High Risk
    8. looking at confusion matrix values, we can see that there are 102 High Risk values predicted as Low Risk
    9. if we are performing this analysis for a financial institution, it is important to consult them about these numbers and if these values are not in their margin of risk, we need to modify the modle and machine learning process by using:
        a. different machine learning modles
        b. tuning of hyperparameters