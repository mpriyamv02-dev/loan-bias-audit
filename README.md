# Loan Approval Bias Audit

## Problem
This project audits a loan approval classification model to evaluate whether predictions differ across demographic groups.

## Dataset
UCI Credit Approval Dataset.

## Approach
- Data cleaning and preprocessing
- Baseline logistic regression model
- Group-based error analysis

## Key Findings
The model predicts loan approval at different rates across demographic groups.

A measurable gap exists in the predicted approval probability between groups labeled a and b.

False negative rates also differ by group, indicating uneven error distribution:

One group experiences a higher rate of denied approvals among applicants who should have been approved.

These results suggest that even a simple, commonly used model can exhibit group-level disparities when trained on real-world credit data.

## Limitations
The dataset uses anonymized categorical labels, limiting real-world interpretability.

The analysis is based on a single baseline model without fairness constraints.

No causal claims are made; observed disparities may reflect historical patterns in the data.

Results depend on preprocessing choices such as encoding and imputation strategy.


## Next Steps
Compare results with and without protected attributes included in the model

Evaluate additional fairness metrics (e.g., equal opportunity difference)

Test alternative models and threshold adjustments

Explore mitigation strategies such as reweighting or post-processing corrections

## How to Run
1. Clone the repository.
2. Ensure the dataset is available at `data/credit_approval.csv`.
3. Open `notebooks/bias_audit.ipynb` in Jupyter or VS Code.
4. Run all cells from top to bottom.

## Why This Project Matters
Machine learning models are often evaluated using aggregate performance metrics such as accuracy or F1 score. However, these metrics can mask differences in how models behave across demographic groups.

This project demonstrates that even a simple, commonly used model trained with a standard preprocessing pipeline can produce uneven outcomes and error rates across groups. Conducting bias audits alongside traditional evaluation is, therefore, a necessary step in responsible model deployment, particularly in high-stakes domains such as lending.
