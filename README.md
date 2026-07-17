# Credit Risk Modeling using Logistic Regression

## Project Overview

This project presents an end-to-end **Credit Risk Modeling** workflow for predicting loan default using **Logistic Regression**. The objective is to estimate the probability of borrower default before loan approval and support data-driven lending decisions through an interpretable scorecard-style model. :contentReference[oaicite:0]{index=0}

The project follows a complete banking analytics pipeline, including business-oriented preprocessing, feature engineering, statistical validation, WOE transformation, leakage detection, model development, and performance evaluation.

---

## Business Objective

Financial institutions face the challenge of identifying high-risk borrowers while maintaining a healthy loan portfolio. This project aims to:

- Predict the probability of loan default.
- Identify key borrower characteristics associated with credit risk.
- Build an interpretable model suitable for lending decisions.
- Segment borrowers based on predicted risk.

---

## Dataset

The dataset contains borrower demographic, financial, and loan-related information used to model loan default behaviour. Missing values were treated using business-driven imputation strategies before analysis. :contentReference[oaicite:1]{index=1}

---

## Project Workflow

1. Data Cleaning & Missing Value Treatment
2. Exploratory Data Analysis (EDA)
3. Feature Engineering
4. Statistical Feature Selection
   - Chi-Square Test
   - Mann–Whitney U Test
5. Weight of Evidence (WOE) Transformation
6. Information Value (IV) Analysis
7. Leakage Detection
8. Multicollinearity Check (VIF)
9. Logistic Regression Modeling
10. Model Evaluation
11. KS Statistic
12. Decile Analysis
13. Variable Importance

---

## Feature Engineering

The following business-oriented variables were engineered:

- Loan-to-Income Ratio
- Property Cushion Percentage
- High DTI Flag
- High Income Flag
- Large Loan Flag

These variables improve model interpretability by capturing borrower affordability, leverage, and repayment capacity.

---

## Statistical Techniques

- Chi-Square Test
- Mann–Whitney U Test
- Weight of Evidence (WOE)
- Information Value (IV)
- Variance Inflation Factor (VIF)
- Logistic Regression

---

## Model Evaluation

The final model was evaluated using:

- ROC-AUC
- Gini Coefficient
- KS Statistic
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Decile Analysis

### Final Model Performance

| Metric | Value |
|---------|-------|
| ROC-AUC | **0.7488** |
| Gini | **0.4977** |
| KS Statistic | **0.3832** |
| Optimal Threshold | **0.2951** |

These results indicate satisfactory discriminatory power for an interpretable credit risk scorecard model. :contentReference[oaicite:2]{index=2}

---

## Business Insights

Key findings include:

- Loan-to-Value (LTV) emerged as one of the strongest predictors of default.
- Borrowers with higher repayment burden exhibited higher default risk.
- Negative amortization significantly increased credit risk.
- Decile analysis effectively ranked borrowers according to default probability.
- Leakage detection substantially improved model reliability before final deployment. :contentReference[oaicite:3]{index=3}

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- SciPy
- ScorecardPy

---

## Repository Structure

```
├── data/
├── notebook/
│   └── Credit_Risk_Model.ipynb
├── report/
│   └── Project_Report.pdf
├── images/
├── requirements.txt
└── README.md
```

---

## Future Improvements

- Gradient Boosting Models
- XGBoost
- Probability Calibration
- Hyperparameter Optimization
- Scorecard Scaling
- Population Stability Index (PSI)

---

## Author

**Ishita Mitra**

M.Sc. Statistics  
Interested in Credit Risk Analytics, Statistical Modeling, and Data Analytics.
