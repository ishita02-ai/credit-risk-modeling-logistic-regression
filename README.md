```markdown
# Loan Default Prediction

End-to-end statistical modeling pipeline to predict the probability of borrower default on a real-world residential mortgage loan portfolio, combining rigorous statistical validation with business-driven feature engineering.

---

## Objective

Identify borrowers at higher risk of default and build a statistically sound, interpretable predictive model that a credit risk team could realistically use to prioritize applications for review — while explicitly testing for and correcting data leakage rather than reporting an inflated headline metric.

---

## Dataset

- **148,670** residential mortgage loan records
- **34** original features
- **Target variable:** `Status` — Good (0) / Default (1)
- **Class split:** 75.4% Good, 24.6% Default

---

## Project Workflow

1. **Data Cleaning & Imputation** — Handled missing values (income, rate_of_interest, property_value, Upfront_charges, Interest_rate_spread, dtir1) using distribution-aware, bucket-based imputation (e.g. median values grouped by loan-amount × income buckets) instead of simple global mean/median fills. LTV was recomputed directly from its definition rather than imputed. Dropped low-value/near-constant identifier fields.

2. **Exploratory Data Analysis** — Profiled default rates across region, loan purpose, income quartile, LTV bucket, and credit score band to surface intuitive risk drivers.

3. **Feature Engineering** — Engineered `loan_income_ratio` as a direct affordability measure, plus three candidate features tested as explicit hypotheses rather than assumed useful:
   - `payment_ratio` (loan_amount / term)
   - `leverage_score` (dtir1 × loan_income_ratio)
   - `credit_type_mismatch` (applicant vs. co-applicant credit-reporting agency)

4. **Statistical Significance Testing** — Chi-Square tests (categorical variables) and Mann-Whitney U tests (continuous variables) against `Status`, keeping only statistically significant predictors (p < 0.05).

5. **Weight of Evidence (WOE) & Information Value (IV)** — Transformed all predictors via WOE and ranked by IV to quantify standalone predictive strength; dropped negligible-IV variables.

6. **Multicollinearity Control (VIF)** — Applied Variance Inflation Factor analysis to the WOE-encoded feature set to eliminate redundant, highly correlated predictors.

7. **Data Leakage Audit** — Built an initial model, diagnosed unrealistically strong performance as target leakage from fields set at/after the underwriting decision, removed them, and retrained on a leakage-free feature set.

8. **Predictive Modeling** — Final interpretable Logistic Regression model, evaluated on a held-out 30% test set.

---

## Tech Stack

- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- scipy
- statsmodels
- scorecardpy

---

## Results

**Model discriminatory power:**

| Metric | Value |
|---|---|
| ROC-AUC | 0.754 |
| Gini Coefficient | 0.507 |
| KS Statistic | 0.388 (optimal threshold = 0.304) |

**Decile risk ranking (business interpretation):**

- The riskiest decile alone shows a **67% default rate** and captures **27% of all defaults** in the portfolio
- The **top 3 riskiest deciles together capture ~59% of all defaults**, while covering only 30% of the loan pipeline
- Enables risk teams to prioritize the highest-risk ~30% of applications for manual underwriting review, independent of the exact classification threshold used

**Classification performance:**

At the standard 0.5 threshold:

| Class | Precision | Recall | F1-score |
|---|---|---|---|
| Good (0) | 80.4% | 95.0% | 87.1% |
| Default (1) | 65.8% | 29.2% | 40.5% |

At the KS-optimal threshold (0.304) — trading precision for materially better default detection:

| Class | Precision | Recall | F1-score |
|---|---|---|---|
| Default (1) | 49.4% | 58.5% | 53.5% |

**Overall Accuracy: 78.8%**

Threshold choice is a business decision, not just a statistical one — the standard 0.5 cutoff favors overall accuracy, while the KS-optimal cutoff favors catching more true defaults.

---

## Key Learning Outcomes

- Credit Risk Analytics
- Statistical Modeling
- Logistic Regression
- Feature Engineering
- Weight of Evidence (WOE)
- Information Value (IV)
- Multicollinearity Analysis
- Data Leakage Detection & Correction
- Model Evaluation (ROC-AUC, Gini, KS, Precision/Recall)
- Decile Analysis
- Business Interpretation of Predictive Models

---

## Future Improvements

- Compare Logistic Regression with tree-based ensemble models.
- Perform probability calibration for improved risk estimation.
- Build an interactive dashboard for model predictions and portfolio monitoring.
- Incorporate model explainability techniques such as SHAP for feature-level interpretation.

---

## Author

**Ishita Mitra**

M.Sc. Statistics | Presidency University, Kolkata

Interested in **Credit Risk Analytics**, **Statistical Modeling**, **Risk Analytics**, and **Data Analytics**.
```
