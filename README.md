# Credit Risk Modeling

```
├── Image                       
│
├── Code_                             <- code
├── README.md                                         <- read me
├── ab    <- dataset
```

https://colab.research.google.com/drive/1sjorLY3Gg316VVW4skgM4kHrUficsYoU#scrollTo=lyQgPcbBk1Ip

## Summary

## 1. Business Understanding
Credit risk modeling is essential for lenders to assess the likelihood that a borrower will default on a loan. Machine learning techniques can be a powerful tool for credit risk modeling because they can identify complex patterns in data that would be difficult to identify with traditional methods. By using machine learning to predict loan default, lenders can make more informed decisions about whether or not to approve loans and at what interest rate. This can help lenders to reduce their risk of loss and improve their profitability.

## 2. Data Understanding
- Data source: Datacamp, including 32581 rows 13 columns
  
- Data Dictionary
  
| Field                    | Datatype   | Definition                                                          | Note                       |
|--------------------------|------------|---------------------------------------------------------------------|----------------------------|
| application_id           | Integer    | Unique identifier for the loan application                          | identifier                 |
| person_age               | Integer    | Age of the loan applicant in years                                  | application data           |
| person_income            | Integer    | Annual income of the loan applicant                                 | behavior data              |
| person_home_ownership    | String     | Ownership status of the loan applicant's home (RENT, MORTGAGE, OWN) | application data           |
| person_emp_length        | Float      | Length of employment of the loan applicant in years                 | application data           |
| loan_intent              | String     | Purpose of the loan (PERSONAL, EDUCATION, MEDICAL)                  | application data           |
| loan_grade               | String     | Grade assigned to the loan based on creditworthiness (A, B, C, D, E)| application data           |
| loan_amt                 | Integer    | Loan amount requested by the applicant                              | application data           |
| loan_int_rate            | Float      | Interest rate of the loan                                           | application data           |
| loan_status              | String     | Status of the loan (Y - Approved, N - Denied)                       | Target variable            |
| loan_percent_income      | Float      | Ratio of the loan amount to the applicant's annual income           | behavior data              |
| ch_person_default_on_file | String (Y/N) | Indicates if the applicant has a history of loan default         | behavior data              |
| ch_person_cred_hist_length| Float      | Length of the applicant's credit history in years                  | behavior data              |
  
- Data issue
  - Abnormal & outlier data
  - Missing data
  - Imbalance data 
## 3. Data Preparation
- Remove abnormal & outlier data
- Fill missing data with median
- Undersampling the non-default data to ensure the balance of training data
- Split train, validation, test data

## 4. Modeling
- Logistic Regression
- XGBoosing

| Model            | Advantage        | Disadvantage    |
|------------------|-----------------------------|-------------------------------------------------------|
| Logistic Regression | - Interpretable: Easy to understand. <br> - Fast training and prediction <br> - Good for binary classification| - Assumes linear relationship <br> - Limited to linear decision boundaries <br> - Sensitive to outliers <br> - Limited expressiveness: Cannot capture complex patterns |
| XGBoost             | - High predictive performance <br> - Handles missing values <br> - Handles nonlinear relationships| - Prone to overfitting <br>- Longer training time <br>- Black-box nature|      
 
## 5. Evaluation
- Model comparison

| Model                | Accuracy | AUC  | F1 (Default)  |
|----------------------|----------|------|------|
| Logistic Regression  | 0.69     | 0.73 | 0.53 |
| XGB Classifier       | 0.89     | 0.86 | 0.76 |

- ROC / AUC curve

![image](https://github.com/Taweilo/credit_risk_modeling/assets/111590843/1f2d3730-df4e-49c0-9738-823adecd0856)

## 6. Recommendation
1. Retrain the model and test model performance on test data

|             | precision | recall | f1-score | support |
|-------------|-----------|--------|----------|---------|
| Non-Default | 0.94      | 0.93   | 0.94     | 4581    |
| Default     | 0.77      | 0.80   | 0.78     | 1312    |
|-------------|-----------|--------|----------|---------|
| accuracy    |           |        | 0.90     | 5893    |
| macro avg   | 0.85      | 0.86   | 0.86     | 5893    |
| weighted avg| 0.90      | 0.90   | 0.90     | 5893    |
   
2. confusion matrix/ ROC AUC curve
   
![image](https://github.com/Taweilo/credit_risk_modeling/assets/111590843/db20fd13-d64f-45ce-a292-0012f932c5f5)

![image](https://github.com/Taweilo/credit_risk_modeling/assets/111590843/8bbbb0bb-67bd-4e9d-b3e7-de83e393d28e)
   
3. Strategy table

|   Acceptance Rate |   Threshold |   Bad Rate |
|------------------:|------------:|-----------:|
|               1.00 |       1.000 |      0.223 |
|               0.95 |       0.994 |      0.183 |
|               0.90 |       0.981 |      0.137 |
|               0.85 |       0.901 |      0.088 |
|               0.80 |       0.590 |      0.065 |
|               0.75 |       0.459 |      0.056 |
|               0.70 |       0.373 |      0.046 |
|               0.65 |       0.314 |      0.039 |
|               0.60 |       0.270 |      0.033 |
|               0.55 |       0.231 |      0.029 |
|               0.50 |       0.202 |      0.026 |
|               0.45 |       0.174 |      0.020 |
|               0.40 |       0.149 |      0.016 |
|               0.35 |       0.125 |      0.011 |
|               0.30 |       0.104 |      0.010 |
|               0.25 |       0.079 |      0.005 |
|               0.20 |       0.048 |      0.002 |
|               0.15 |       0.020 |      0.000 |
|               0.10 |       0.007 |      0.000 |
|               0.05 |       0.004 |      0.000 |
   
5. Total expected loss = SUM(probability of default * Exposure at default * Loss given default) = $19,757,146.02
## 7. Future Improvement
- Calibration curve
  Even though the model has a high AUC, the predicted probability is higher than expected (underconfidence). We recommend clibrating the error. 
![image](https://github.com/Taweilo/credit_risk_modeling/assets/111590843/02361893-749f-402a-82a6-e0a3690a2908)

