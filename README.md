# Race/Gender Fairness Simulation 

![screenshot-localhost_8888-2025 04 04-14_16_05](https://github.com/user-attachments/assets/778d0423-e1b5-4ec7-88e4-aa774be2a219)

### Overview

This project implements a credit scoring model using logistic regression and conducts a fairness analysis to assess potential biases across simulated demographic groups (race, gender). Key components:

- Data simulation (income, geography → proxy race/gender variables)
- Credit scorecard development (Logistic Regression + scaling to score points)
- Comprehensive fairness testing (disparate impact, statistical parity, AUC by subgroup)

### Dataset

Target: SeriousDlqin2yrs (1 = default within 2 years, 0 = no default)

**Key Features Used**

- Feature Risk Impact
- RevolvingUtilizationOfUnsecuredLines (Hig)h
- TotalPastDue (engineered) (Very High)
- NumberOfTimes90DaysLate (High)
- MonthlyIncome (Medium)
- age (Low)

### Key Features

1. Data Simulation
- Simulates race/gender based on income quintiles and geographic clusters.
- Models intersectional groups (e.g., "Minority Female") and "thin credit file" status.

2. Credit Scorecard
- Logistic Regression model trained on financial features (income, debt ratio, payment history).
- Converts probabilities to interpretable scores (base=600, PDO=50).

3. Fairness Metrics
- Disparate Impact Ratio (threshold: <0.8 indicates bias)
- Statistical Tests (t-tests for score differences)
- Performance Equity (AUC, approval rates by subgroup)
- Root Cause Analysis (features contributing to disparities)

### Results Summary

- Model AUC	0.55 (weak predictive power)
- Race Disparity	Ratio=1.11 (no adverse impact)
- Gender Disparity	Ratio=1.02 (no bias detected)
- Highest Scores	Minority Female (602.05)

Unexpected Insight: Minority groups received higher approval rates than non-minorities—contrary to real-world trends.

### Limitations

- Synthetic Data: Simulated demographics may not reflect real-world distributions.
- Model Performance: Low AUC suggests weak predictive power.
- Bias Detection: Further metrics (e.g., equalized odds) could strengthen analysis.

### Source

[Give Me Some Credit Dataset from Kaggle](https://www.kaggle.com/c/GiveMeSomeCredit)
  

