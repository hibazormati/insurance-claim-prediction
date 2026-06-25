# 🚗 Insurance Claim Prediction
 
End-to-end machine learning pipeline for predicting automobile insurance claim occurrence based on customer, vehicle, and policy data.
 
---
 
## Overview
 
Insurance companies rely on accurate risk assessment to set pricing strategies and minimize financial exposure. This project builds a **binary classification model** to predict whether a customer will file a claim, using a real-world automobile insurance dataset of 58,000+ policies.
 
**Task:** Predict `claim_status` — whether a customer files an insurance claim.
 
---
 
## Dataset
 
Automobile insurance dataset containing customer demographics, vehicle characteristics, policy details, geographic information, and claim history.
 
| Property | Value |
|---|---|
| Records | 58,000+ policies |
| Target | `claim_status` (binary) |
| Feature types | Numerical, categorical, binary flags |
 
Key feature groups: customer demographics (age, region), vehicle specs (displacement, power, torque, airbags, NCAP rating), policy info (subscription length, segment), and safety features (ESC, TPMS, parking sensors, brake assist, etc.).
 
---
 
## Pipeline
 
```
1. Data Understanding
         ↓
2. Data Quality Assessment
         ↓
3. Exploratory Data Analysis (EDA)
         ↓
4. Feature Engineering
         ↓
5. Feature Selection
         ↓
6. Modeling & Evaluation
         ↓
7. Interpretation
```
 
| Step | Techniques |
|---|---|
| Data Quality | Missing value analysis, duplicate detection, type correction |
| Feature Engineering | Torque/power extraction from raw strings, zero-value categorization, type reclassification (width, cylinder → categorical) |
| EDA | Univariate & multivariate analysis, claim rate by segment, correlation analysis (point-biserial, Chi²) |
| Feature Selection | Statistical filtering, Cramér's V, ANOVA |
| Modeling | Logistic Regression (+ additional models) |
| Evaluation | AUC-ROC, F1-Score, Precision, Recall, Gini, KS statistic |
 
---
 
## Notable Engineering Decisions
 
- `width` and `cylinder` reclassified as categorical variables due to low cardinality
- Zero values in `subscription_length` and `vehicle_age` preserved as separate categories (carry real-world meaning: new policy / new vehicle)
- Torque and power parsed from raw strings (`"250Nm@2750rpm"` → `torque_value`, `torque_rpm`)
---
 
## Tech Stack
 
- **Python** — pandas, numpy, scikit-learn
- **Visualization** — matplotlib, seaborn
- **Statistics** — scipy
---
 
## Project Structure
 
```
insurance-claim-prediction/
├── e5erversionatelier__7_.ipynb   # Main analysis notebook
├── Insurance-claims-data.csv      # Dataset (not included)
└── README.md
```
 
---
 
## Author
 
**Hiba** — Data Science student at ESSAI  
Portfolio project — Insurance Risk Modeling & Predictive Analytics
