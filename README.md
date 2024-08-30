# Credit-Card-Fraud-Prediction

## Project Overview

This project focuses on developing a machine learning model to detect fraudulent credit card transactions. Given the critical nature of fraud detection in financial systems, the goal is to build a robust model that effectively identifies fraudulent transactions while minimizing false positives to ensure legitimate transactions are not incorrectly flagged.

## Dataset

- **Source**: The dataset can be found on Kaggle: [Credit Card Fraud Prediction Dataset](https://www.kaggle.com/datasets/kelvinkelue/credit-card-fraud-prediction/data)
- **Attributes**:
  - `cc_num`: Unique customer identification number.
  - `category`: Transaction type (e.g., personal, childcare).
  - `amt`: Transaction amount.
  - `gender`: Cardholder's gender.
  - `state`: Cardholder's state of residence.
  - `zip`: Cardholder's zip code.
  - `city_pop`: Population of the cardholder's city.
  - `job`: Cardholder's job title.
  - `unix_time`: Transaction timestamp (Unix format).
  - `is_fraud`: Fraudulent transaction indicator (1 = fraud, 0 = legitimate). This is the target variable.

## Models and Evaluation

### Models Implemented:
- **Decision Tree**
- **Logistic Regression**
- **Random Forest**
- **LightGBM**
- **CatBoost**
- **XGBoost (Final Model)**

### Evaluation Metrics:
- **Confusion Matrix**: Used to visualize the model's performance by showing the distribution of true positives (TP), true negatives (TN), false positives (FP), and false negatives (FN).
- **ROC & AUC**: Measures the ability of the model to distinguish between fraudulent and legitimate transactions.
- **Precision-Recall Curve & AUC**: Particularly useful in dealing with imbalanced datasets like fraud detection, showing the trade-off between precision and recall.

### Final Model: XGBoost
- **Confusion Matrix**:
  - TP = 535
  - TN = 166,048
  - FP = 28
  - FN = 105
- **Accuracy**: 99.92%
- **ROC AUC**: 1.00
- **Precision-Recall AUC**: 0.94

## Feature Importance
- The most significant features identified in the XGBoost model were:
- `Trans_date_trans_time`: Timestamp of the transaction (date and time).
  - `Cc_num`: Unique customer identification number.
  - `Merchant`: The merchant involved in the transaction.
  - `Category`: Transaction type (e.g., personal, childcare).
  - `Amt`: Transaction amount.
  - `First`: Cardholder's first name.
  - `Last`: Cardholder's last name.
  - `Gender`: Cardholder's gender.
  - `Street`: Cardholder's street address.
  - `City`: Cardholder's city of residence.
  - `State`: Cardholder's state of residence.
  - `Zip`: Cardholder's zip code.
  - `Lat`: Latitude of cardholder's location.
  - `Long`: Longitude of cardholder's location.
  - `City_pop`: Population of the cardholder's city.
  - `Job`: Cardholder's job title.
  - `Dob`: Cardholder's date of birth.
  - `Trans_num`: Unique transaction identifier.
  - `Unix_time`: Transaction timestamp (Unix format).
  - `Merch_lat`: Merchant's location (latitude).
  - `Merch_long`: Merchant's location (longitude).
  - `Is_fraud`: Fraudulent transaction indicator (1 = fraud, 0 = legitimate). This is the target variable for classification purposes.

## Business Impact

The model's recall of 83.59% indicates that it successfully identifies approximately 83.6% of all fraudulent transactions. This has significant business implications, including:
- **Fraud Loss Reduction**: Estimated annual savings of $8.36 million, assuming a total potential fraud loss of $10 million without detection measures.
- **Operational Efficiency**: Focusing resources on likely fraud cases while balancing the workload by minimizing false positives.
- **Improved Customer Trust**: Protecting customers from unauthorized charges by catching the majority of fraudulent transactions.

### Potential Improvements
- **Increase Recall**: Further model tuning or additional features could improve the recall rate, reducing the number of missed fraudulent transactions.
- **Safety Net Rules**: Implement rule-based systems to catch fraud cases the model might miss, ensuring comprehensive coverage.

## Fraud Strategy Proposal

- **Final Fraud Strategy**: Optimize the model's fraud detection capabilities by balancing recall and precision, ensuring high fraud coverage while minimizing false positives.
- **Safety Net Rules**: In case of model timeouts or other issues, deploy simple, rule-based fraud detection mechanisms to maintain coverage.
- **Fraud Hit Rate and Coverage Rate**: Maximize these rates to ensure effective fraud detection while minimizing customer impact.

## Getting Started

To replicate this project:
1. Clone the repository.
2. Install the required Python libraries (e.g., `xgboost`, `lightgbm`, `catboost`, `scikit-learn`).
3. Run the Jupyter notebooks provided to train the models and evaluate their performance.

## Assumptions and Limitations

- **Data Assumptions**: Assumes no missing values and that all relevant features are included.
- **Model Limitations**: The model's effectiveness is contingent on the quality and representativeness of the training data.

## Conclusion

This project provides a comprehensive approach to detecting credit card fraud using machine learning. The final XGBoost model offers a strong balance of precision and recall, with significant potential business impact in reducing fraud losses and improving customer trust.
