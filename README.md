# D2C Customer Churn Intelligence & Retention

## Part 3 – Churn Prediction Modeling

---

## Project Overview

This repository contains the predictive modeling phase of the D2C Customer Churn Intelligence project.

The objective of this phase is to develop a machine learning model capable of identifying customers at risk of churning within the next 60 days, enabling proactive retention interventions and more efficient allocation of retention resources.

The model transforms customer behavioral, transactional, engagement, and loyalty signals into customer-level churn risk scores.

---

## Business Objective

Customer acquisition costs continue to increase across the D2C industry, making customer retention a critical business priority.

The goal of this project is to:

- Predict future customer churn.
- Identify high-risk customers before they disengage.
- Support targeted retention campaigns.
- Improve customer lifetime value (CLV).
- Reduce unnecessary retention spending.

---

## Repository Structure

```text
.
├── notebooks/
│   └── churn_model.ipynb
│
├── metrics/
│   ├── feature_importance.csv
│   ├── model_metrics.csv
│   └── risk_scores.csv
│
├── models/
│   └── best_model.pkl
│
├── reports/
│   ├── model_card.md
│   └── error_analysis.md
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Dataset

The modeling process uses:

- rfm_modeling_snapshot.csv
- churn_labels.csv

The modeling dataset contains customer-level features generated from historical behavioral and transactional activity prior to the churn observation window.

### Dataset Summary

| Metric | Value |
|----------|----------:|
| Customers | 2,400 |
| Features | 29 |
| Target Variable | churn_next_60d |
| Train Records | 1,728 |
| Validation Records | 336 |
| Test Records | 336 |

---

## Modeling Methodology

### 1. Data Preparation

The modeling dataset was reviewed to:

- validate feature availability,
- verify target balance,
- identify non-feature columns,
- prevent target leakage.

Excluded columns:

- customer_id
- snapshot_date
- split
- churn_next_60d

Categorical variables were encoded using one-hot encoding.

---

### 2. Train / Validation / Test Split

A predefined split strategy provided within the dataset was used:

| Split | Records |
|----------|----------:|
| Train | 1,728 |
| Validation | 336 |
| Test | 336 |

This approach mirrors real-world production workflows and avoids random resampling.

---

### 3. Models Evaluated

#### Logistic Regression

Used as a baseline model due to:

- interpretability,
- simplicity,
- deployment readiness.

#### Random Forest

Used to evaluate whether nonlinear relationships could improve churn prediction performance.

---

## Model Evaluation

### Logistic Regression

| Metric | Score |
|----------|----------:|
| Accuracy | 0.8185 |
| Precision | 0.8116 |
| Recall | 0.7619 |
| F1 Score | 0.7860 |
| ROC-AUC | 0.8841 |

---

### Random Forest

| Metric | Score |
|----------|----------:|
| Accuracy | 0.7917 |
| Precision | 0.7939 |
| Recall | 0.7075 |
| F1 Score | 0.7482 |
| ROC-AUC | 0.8781 |

---

## Final Model Selection

### Selected Model

```text
Logistic Regression
```

### Selection Rationale

Logistic Regression achieved superior performance across all key evaluation metrics, including:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

Additionally, the model offers greater interpretability and simpler deployment compared to more complex ensemble models.

---

## Feature Importance Analysis

The model identified several factors associated with churn risk.

Examples include:

- Loyalty participation
- Acquisition channel
- Marketing consent
- Product category preferences
- Customer engagement behavior
- Transaction activity patterns

Detailed results are available in:

```text
metrics/feature_importance.csv
```

---

## Risk Scoring Framework

The selected model generates customer-level churn probabilities.

Customers are grouped into:

| Risk Band | Probability Range |
|----------|----------|
| Low Risk | 0.00 – 0.30 |
| Medium Risk | 0.30 – 0.60 |
| High Risk | 0.60 – 1.00 |

These risk categories can be used to prioritize retention interventions.

---

## Project Outputs

### Metrics

- model_metrics.csv
- feature_importance.csv

### Customer Risk Scores

- risk_scores.csv

### Trained Model

- best_model.pkl

### Reports

- model_card.md
- error_analysis.md

---

## Key Findings

### High Predictive Performance

The selected model achieved a ROC-AUC score of approximately 0.88, demonstrating strong ability to distinguish between customers likely to churn and those likely to remain active.

### Interpretable Predictions

Logistic Regression provides transparent decision logic, making it easier for business stakeholders to understand and trust model outputs.

### Actionable Risk Segmentation

Customer-level risk scores enable retention teams to prioritize intervention efforts toward customers with the highest expected churn risk.

---

## Business Recommendations

### High-Risk Customers

Recommended actions:

- Win-back campaigns
- Personalized retention offers
- CRM outreach

### Medium-Risk Customers

Recommended actions:

- Product recommendations
- Loyalty engagement campaigns
- Personalized promotions

### Low-Risk Customers

Recommended actions:

- Standard engagement programs
- Routine retention monitoring

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Joblib
- Jupyter Notebook

---

## Conclusion

A machine learning-based churn prediction framework was successfully developed and evaluated.

Logistic Regression emerged as the best-performing model, achieving strong predictive performance while maintaining interpretability and deployment simplicity.

The resulting churn risk scores provide a practical foundation for retention targeting, customer prioritization, and operational decision-making in future phases of the D2C Customer Churn Intelligence project.