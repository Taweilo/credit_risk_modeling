# Credit Risk Modeling

```
├── Image                       
│
├── Code_                             <- code
├── README.md                                         <- read me
├── ab    <- dataset
```

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
- Abnormal & outlier data
- Fill missing data with median
- Undersampling the non-default data to ensure the balance of training data
- Split train, validation, test data

## 4. Modeling
- Logistic Regression
- XGBoosing

| Model            | Advantage        | Disadvantage    |
|------------------|-----------------------------|-------------------------------------------------------|
| Logistic Regression | - Interpretable: Easy to understand. <br>
                        - Fast training and prediction: Efficient for large datasets <br>
                        - Good for binary classification
                        |
 - Assumes linear relationship: Might not capture complex interactions between features <br>
 - Limited to linear decision boundaries <br>
 - Sensitive to outliers <br>
 - Limited expressiveness: Cannot capture complex patterns
 |
| XGBoost             | - High predictive performance | Prone to overfitting|      
 
## 5. Evaluation

## 6. Recommendation

## 7. Conclusion
