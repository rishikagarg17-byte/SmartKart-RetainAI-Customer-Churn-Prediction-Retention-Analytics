# SmartKart-RetainAI-Customer-Churn-Prediction-Retention-Analytics
# SmartKart RetainAI — Customer Churn Prediction & Retention Analytics

## 📌 Project Overview

SmartKart RetainAI is an end-to-end machine learning project designed to identify customers who are most likely to churn.

The project uses customer-level data such as:

- Age
- Monthly Spend
- Number of Complaints
- Churn status

A Logistic Regression model is trained to predict whether a customer is likely to leave SmartKart. The final output converts these predictions into an actionable churn-risk report that can help a business prioritize customer retention efforts.

---

## 🎯 Business Objective

Customer churn can directly impact revenue and long-term customer relationships.

The objective of this project is to:

1. Clean and prepare raw customer data.
2. Identify meaningful factors associated with churn.
3. Build a machine learning model to predict churn.
4. Evaluate the model using classification metrics.
5. Generate churn probabilities for individual customers.
6. Identify high-risk customers for immediate retention action.

---

## 🧠 Machine Learning Approach

The project follows a complete 15-step machine learning pipeline:

### 1. Data Loading
The SmartKart customer dataset is loaded and inspected.

### 2. Data Understanding
The structure, data types, missing values, duplicates, and potential data-quality issues are examined.

### 3. Data Cleaning
Invalid and missing values are handled.

Examples include:
- Converting Age into a numeric format
- Handling invalid ages
- Replacing negative Monthly Spend values
- Filling missing values using the median
- Removing duplicate records

### 4. Outlier Detection & Treatment
The IQR (Interquartile Range) method is used to detect extreme values.

Instead of deleting affected customers, outliers are capped to preserve the remaining customer information.

### 5. Feature Selection
The following business-relevant features are selected:

- `Age`
- `Monthly_Spend`
- `Complaints`

`Customer_ID` is excluded from model training because it is an identifier rather than a predictive feature.

### 6. Target Definition
The target variable is:

`Churn`

Where:

- `0` = No Churn
- `1` = Churn

### 7. Target Verification
The churn variable is verified to ensure it is already stored in numeric 0/1 format.

### 8. Train-Test Split
The dataset is divided into:

- 80% Training Data
- 20% Testing Data

Stratification is used to maintain a similar churn ratio in both datasets.

### 9. Feature Standardisation
`StandardScaler` is used to standardise the numerical features.

The scaler is fitted only on the training data and then applied to the test data to prevent data leakage.

### 10. Model Building
A Logistic Regression classifier is selected because churn is a binary classification problem.

### 11. Model Training
The model learns the relationship between customer characteristics and churn behaviour using the training dataset.

### 12. Prediction
The trained model generates:

- Predicted churn class
- Churn probability

The probability score is particularly useful for ranking customers according to their risk level.

### 13. Model Evaluation
The model is evaluated using:

- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report

### 14. Model Interpretation
The model coefficients are analysed to understand which factors are associated with higher or lower churn risk.

Key business insights from the analysis include:

- Higher Monthly Spend is associated with lower churn risk.
- A higher number of Complaints is associated with higher churn risk.
- Age has a comparatively smaller impact on churn in this dataset.

### 15. Business-Ready Output
The model produces a ranked customer churn-risk report containing:

- Customer ID
- Age
- Monthly Spend
- Complaints
- Actual Churn
- Predicted Churn
- Churn Probability
- Risk Label

Customers are ranked from highest to lowest churn probability so that retention teams can prioritise their efforts.

---

## 📊 Dataset

The project uses a 100-record SmartKart customer dataset containing intentionally introduced data-quality issues to simulate a real-world business dataset.

During preprocessing:

- Duplicate records are removed.
- Invalid values are identified and corrected.
- Missing numerical values are imputed using medians.
- Extreme values are treated using IQR-based capping.

After preprocessing, the cleaned dataset contains 95 customer records.

---

## 🔍 Key Business Insights

The model provides more than just a prediction — it helps identify potential retention strategies.

### Complaints → Higher Churn Risk

Customers with more complaints show increased churn risk.

**Business action:**  
SmartKart could improve complaint resolution, response times, and customer-support processes.

### Monthly Spend → Lower Churn Risk

Higher-spending customers show lower predicted churn risk in this dataset.

**Business action:**  
High-value customers should receive continued engagement and relationship-building initiatives.

### Age → Smaller Effect

Age has a relatively weaker relationship with churn compared with Monthly Spend and Complaints.

---

## 📈 Model Performance

The notebook evaluates the Logistic Regression model using standard classification metrics.

The test-set results are designed to assess how effectively the model identifies customers who may churn, with particular attention to **Recall**, since failing to identify a genuine churner may represent a lost retention opportunity.

> Note: Exact performance metrics should be taken from the executed notebook output rather than assumed from the expected interpretation.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab
- Logistic Regression

---

## 📂 Project Structure

```text
SmartKart-RetainAI/
│
├── SmartKart_Churn_Prediction_ML_Pipeline.ipynb
├── SmartKart_dirty_100_rows.csv
├── smartkart_churn_risk_report.csv
└── README.md
