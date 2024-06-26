 <h1 align="center">
  Credit Card Fraud Detection 
</h1>
<div align="center">
  <h4>Aurthor: <a href="https://www.linkedin.com/in/kamakshisharma22">Kamakshi Sharma</a></h4>
</div>

This repository contains an analysis of credit card fraud detection using various machine learning techniques. The project explores the trade-off between accuracy and fraud detection capabilities to identify the most suitable model for real-world scenarios.

## Data Description

- Simulated credit card transaction dataset spanning 24 months (January 2019 - December 2020)
- **Number of transactions:** 1,296,675
- **Features:** 23 attributes including transaction details, cardholder information, merchant details, and a fraud indicator.
- **Class imbalance:** 0.6% fraudulent transactions, 99.4% legitimate transactions.

## Approach

1. **Exploratory Data Analysis (EDA) and Data Cleaning**
    - Analyzed data distribution, identified missing values (if any) and data types.
    - Performed data cleaning techniques to address inconsistencies or errors (details provided in the Jupyter Notebook).
    - Analyzed relationships between features and the fraud indicator using visualization techniques.
    - Identified potential outliers and data imbalances.

2. **Data Preprocessing**
    - Converted categorical variables into numerical representations using techniques like one-hot encoding or binary encoding (details in the Jupyter Notebook).
    - Performed standard scaling on numerical features to ensure all features are on a similar scale.
    - Addressed class imbalance using SMOTE (Synthetic Minority Over-sampling Technique) to create synthetic samples for the minority class (fraudulent transactions).

3. **Model Building**
    - Implemented four machine learning models:
     - Machine Learning Technique : 
        - Logistic Regression: Provides interpretable coefficients for understanding feature impact on fraud.
        - Random Forest: Captures complex data relationships for detecting subtle fraud patterns.
     - Anomaly Detection Technique : 
        - Isolation Forest: Efficiently isolates anomalies (fraudulent transactions) in high-dimensional data.
     - Deep Learning Technique : 
        - Neural Network (MLP Classifier): Captures non-linear data patterns for sophisticated fraud detection.
    - Trained and evaluated each model using a stratified split to ensure class representation in the training and testing sets.

4. **Model Comparison:**

| Model             | Accuracy | Precision for Fraud | Recall for Fraud |
|-------------------|----------|---------------------|------------------|
| Logistic Regression | 89%     | 0.04                | 0.76             |
| Random Forest       | 100%    | 1.00                | 1.00             |
| Isolation Forest    | 97%     | 0.01                | 0.03             |
| Neural Network      | 98%     | 0.20                | 0.89             |


5. **Model Performance & Key Findings**
    - Evaluated models using classification reports(Accuracy, Precision, Recall, F1-Score), ROC-AUC scores, ROC curves, and precision-recall curves. Detailed results are provided in the Jupyter Notebook.
    - **Key findings:**
        - Random Forest achieved the highest overall accuracy (100%) but raises concerns about overfitting. However, it performed well in identifying both types of transactions.
        - Logistic Regression had high accuracy but struggled with fraud detection (low precision and recall for fraud class).
        - Isolation Forest achieved high accuracy but poorly identified fraudulent transactions.
        - Neural Network offered a balance between accuracy and fraud detection.
    - **Random Forest** become the best out of four. 

6. **Ensemble Method**
    - To potentially improve fraud detection and reduce overfitting risk, we combined Random Forest and Isolation Forest.
    - This ensemble method achieved promising results:
        - Accuracy: 97% (reduced overfitting risk compared to Random Forest alone).
        - Precision (Fraud): 0.15 (lower than Random Forest but captures more fraud overall).
        - Recall (Fraud): 0.80 (improved compared to Random Forest).

## Overall Results

The analysis suggests that Improved Random Forest i.e, **Ensemble method (Random Forest + Isolation Forest)** is more promising choice for credit card fraud detection due to their balanced performance and ability to identify both normal and fraudulent transactions. However, real-time implementation considerations like model interpretability, computational efficiency, and concept drift need to be addressed for practical deployment.


## GitHub File:
- Jupyter Notebook [click here](https://github.com/kamakshii22/Fraud_Detection/blob/main/Project_Fraud_Detection.ipynb)

## Presentation

The [presentation-ppt](https://github.com/kamakshii22/Fraud_Detection/blob/main/PPT_Fraud_Detection_Kamakshi.pptx) file provides a comprehensive overview of the project, including detailed explanations, figures, and tables. Refer to this file for a deeper understanding of the concepts and findings.


