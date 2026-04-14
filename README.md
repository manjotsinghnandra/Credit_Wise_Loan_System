# Loan Approval Prediction System

## Project Overview
This project builds a Machine Learning pipeline to predict whether a loan application will be approved or not based on applicant financial and demographic details.

The workflow includes:
- Data preprocessing
- Exploratory Data Analysis (EDA)
- Feature engineering
- Model training and evaluation
- Performance comparison

---

## Dataset Information
The dataset contains 1000 records with 20 features, including:

### Numerical Features
- Applicant Income  
- Coapplicant Income  
- Age  
- Dependents  
- Credit Score  
- Existing Loans  
- DTI Ratio  
- Savings  
- Collateral Value  
- Loan Amount  
- Loan Term  

### Categorical Features
- Employment Status  
- Marital Status  
- Loan Purpose  
- Property Area  
- Education Level  
- Gender  
- Employer Category  

### Target Variable
- `Loan_Approved` (Yes/No)

---

## Data Preprocessing

### Handling Missing Values
- Numerical columns: filled using mean
- Categorical columns: filled using most frequent value

### Encoding
- Label Encoding:
  - Education_Level
  - Loan_Approved
- One-Hot Encoding:
  - Remaining categorical features

### Feature Scaling
- Standardization using StandardScaler

---

## Exploratory Data Analysis (EDA)

Key insights:
- Dataset is fairly balanced
- Credit Score has strong influence on approval
- DTI Ratio negatively impacts approval
- Income and savings show moderate impact

Visualizations used:
- Pie charts (class balance)
- Histograms (income distribution)
- Boxplots (outliers and relationships)
- Correlation heatmap

---

## Feature Engineering

New features created:
- `DTI_Ratio_sq` (captures non-linear impact)
- `Credit_Score_sq` (enhances importance of score)

Dropped:
- Original `DTI_Ratio` and `Credit_Score`

---

## Models Used

1. Logistic Regression  
2. K-Nearest Neighbors (KNN)  
3. Naive Bayes (GaussianNB)  

---

## Model Performance (Before Feature Engineering)

| Model               | Accuracy | Precision | Recall | F1 Score |
|---------------------|----------|-----------|--------|----------|
| Logistic Regression | 0.865    | 0.78      | 0.77   | 0.77     |
| KNN                 | 0.76     | 0.62      | 0.52   | 0.57     |
| Naive Bayes         | 0.865    | 0.80      | 0.74   | 0.77     |

Best model (Precision): Naive Bayes

---

## Model Performance (After Feature Engineering)

| Model               | Accuracy | Precision | Recall | F1 Score |
|---------------------|----------|-----------|--------|----------|
| Logistic Regression | 0.875    | 0.79      | 0.80   | 0.79     |
| KNN                 | 0.755    | 0.62      | 0.50   | 0.56     |
| Naive Bayes         | 0.865    | 0.78      | 0.77   | 0.77     | 

Best overall model: Logistic Regression

---

## Key Insights

- Credit Score is the strongest positive predictor  
- DTI Ratio is the strongest negative predictor  
- Feature engineering improved Logistic Regression performance  
- KNN underperformed due to feature scaling sensitivity  

---

## Tech Stack

- Python  
- Pandas and NumPy  
- Seaborn and Matplotlib  
- Scikit-learn  

---

## How to Run

```bash
# Clone repository
git clone https://github.com/your-username/loan-approval-prediction.git

# Install dependencies
pip install -r requirements.txt

# Run the notebook/script
