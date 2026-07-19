# 📊 Loan Default Prediction using Logistic Regression

## Overview

This project develops an interpretable **Loan Default Prediction** model using statistical modeling techniques to identify borrowers with a higher probability of default. The objective is to assist financial institutions in making informed lending decisions by combining rigorous statistical analysis with business-driven feature engineering.

The project follows a complete analytical workflow, including data preprocessing, exploratory data analysis, feature engineering, statistical significance testing, Weight of Evidence (WOE) encoding, Information Value (IV) analysis, multicollinearity assessment, predictive modeling, and business-oriented model evaluation.

---

## Dataset

* **Total Records:** 148,670 mortgage loan applications
* **Original Features:** 34
* **Target Variable:** `Status`

  * **0:** Good Loan
  * **1:** Default

---

## Project Workflow

### 1. Data Preparation

* Removed non-informative variables
* Treated invalid zero values as missing where appropriate
* Performed bucket-based median and mode imputation
* Recalculated Loan-to-Value (LTV) instead of imputing it directly
* Created a clean dataset with minimal missing values

---

### 2. Exploratory Data Analysis

Analyzed default behaviour across multiple borrower characteristics, including:

* Income
* Loan Purpose
* Region
* Loan-to-Value (LTV)
* Credit Score
* Property Value
* Credit Reporting Agency

The analysis helped identify meaningful business patterns before model development.

---

### 3. Feature Engineering

Engineered additional business-relevant variables, including:

* **Loan-to-Income Ratio**
* **Payment Ratio**
* **Leverage Score**
* **Credit Type Mismatch**

Each engineered feature was statistically evaluated before inclusion in the final model.

---

### 4. Statistical Validation

Performed statistical tests to ensure predictor relevance.

**Categorical Variables**

* Chi-Square Test

**Continuous Variables**

* Mann–Whitney U Test

Only statistically significant variables were retained.

---

### 5. Feature Selection

Applied:

* Weight of Evidence (WOE) Encoding
* Information Value (IV) Analysis
* Variance Inflation Factor (VIF)

This helped:

* Measure predictor strength
* Remove weak variables
* Eliminate multicollinearity
* Improve model interpretability

---

### 6. Predictive Modeling

Developed an interpretable **Logistic Regression** model.

Model evaluation included:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC
* Gini Coefficient
* KS Statistic

---

## Final Model Performance

| Metric           |     Value |
| ---------------- | --------: |
| Accuracy         | **78.8%** |
| ROC-AUC          | **0.754** |
| Gini Coefficient | **0.507** |

---

## Business Evaluation

In addition to traditional machine learning metrics, the project includes **Decile Analysis** for practical business interpretation.

The model enables lenders to:

* Rank borrowers according to default risk
* Prioritize high-risk applications for manual review
* Improve underwriting decisions
* Support portfolio risk management
* Allocate resources more efficiently

---

## Technologies Used

### Programming Language

* Python

### Libraries

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* scipy
* statsmodels
* scorecardpy

---

## Key Learning Outcomes

* Credit Risk Analytics
* Statistical Modeling
* Logistic Regression
* Feature Engineering
* Weight of Evidence (WOE)
* Information Value (IV)
* Multicollinearity Analysis
* Model Evaluation
* Decile Analysis
* Business Interpretation of Predictive Models

---

## Future Improvements

* Compare Logistic Regression with tree-based ensemble models.
* Perform probability calibration for improved risk estimation.
* Build an interactive dashboard for model predictions and portfolio monitoring.
* Incorporate model explainability techniques such as SHAP for feature-level interpretation.

---

## Author

**Ishita Mitra**

M.Sc. Statistics | Presidency University, Kolkata

Interested in **Credit Risk Analytics**, **Statistical Modeling**, **Risk Analytics**, and **Data Analytics**.
