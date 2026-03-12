## Project Overview
This project develops a risk-based customer segmentation framework to predict the probability of credit card default. 

The objective is not only to classify default vs. non-default customers, but to:
1. Estimate calibrated probabilities of default (PD)
2. Segment customers into actionable risk groups
3. Validate model performance using credit risk metrics
4. Support risk-aware marketing and portfolio management decisions

The final output is a calibrated probability score that enables strategic targeting and risk mitigation.


## Dataset
Source: 
Taiwan Credit Card Default Dataset (UCI Machine Learning Repository)

Size:
- 30,000 customers
- 24 explanatory variables
- 1 binary target variable (DEFAULT)

Features Included:
- Demographics (Age, Gender, Education, Marriage)
- Credit limit (LIMIT_BAL)
- 6 months of repayment history (PAY_0 to PAY_6)
- 6 months of bill amounts (BILL_AMT1–6)
- 6 months of payment amounts (PAY_AMT1–6)
- Target variable: default payment next month (1 = default, 0 = no default)


## Tools Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

## Models 
Primary Model: Logistic Regression
Comparative Model: Neural Network

Key Modeling Steps:
1. Feature engineering (delinquency severity, utilization, payment ratios, trends)
2. Train/test split (70/30 stratified)
3. Standardization of numeric features
4. Probability calibration using isotonic regression

Validation Metrics:
- Accuracy: ~81%
- KS Statistic: 0.41 (strong discriminatory power)
- Lift (Top Risk Segment): 2.06× average default rate
- Top 20% highest-risk customers capture ~49% of all defaulters
- Calibrated probabilities closely match observed default rates

Key Findings:
- Delinquency severity and frequency are the strongest predictors of default.
- High utilization significantly increases default risk.
- Lower payment-to-bill ratios are associated with financial stress.
- Risk segments show monotonic increases in both predicted and actual default rates.


## Results
The calibrated model successfully separates low-risk and high-risk customers.

Risk segmentation produced five actionable groups:
- Very Low Risk (<5% PD)
- Low Risk (5–10% PD)
- Medium Risk (10–20% PD)
- High Risk (20–40% PD)
- Very High Risk (>40% PD)

The highest-risk segment shows:
- ~45% observed default rate
- 2× lift over portfolio average
- Strong deterioration in delinquency and repayment behavior

The model demonstrates strong ranking power and economically consistent segmentation.
