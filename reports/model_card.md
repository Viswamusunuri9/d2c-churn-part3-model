# Model Card

## D2C Customer Churn Intelligence Project
### Part 3 - Churn Prediction Modeling

---

# Model Overview

This model predicts the probability that a customer will churn within the next 60 days.

The model is intended to support retention decision-making by identifying customers who are most likely to disengage and require proactive intervention.

---

# Business Objective

The objective of the model is to:

- identify high-risk customers,
- prioritize retention resources,
- reduce customer churn,
- improve customer lifetime value.

---

# Target Variable

| Variable | Description |
|----------|----------|
| churn_next_60d | 1 = Customer churns within 60 days, 0 = Customer retained |

---

# Training Dataset

Dataset:

```text
rfm_modeling_snapshot.csv
```

Observations:

```text
2,400 customers
```

Target Distribution:

| Class | Customers |
|----------|----------:|
| Retained (0) | 1273 |
| Churned (1) | 1127 |

---

# Features

The model uses customer-level behavioral, transactional, engagement, and loyalty features including:

- Recency
- Frequency
- Monetary value
- Session activity
- Support interactions
- Loyalty participation
- Acquisition channel
- Product preferences
- Marketing engagement

---

# Models Evaluated

## Logistic Regression

Purpose:

- Baseline model
- High interpretability
- Production-friendly

---

## Random Forest

Purpose:

- Non-linear pattern detection
- Feature interaction modeling

---

# Final Model Selection

Selected Model:

```text
Logistic Regression
```

Reason:

Logistic Regression outperformed Random Forest across key validation metrics and provides greater interpretability for business stakeholders.

---

# Validation Performance

| Metric | Score |
|----------|----------:|
| Accuracy | 0.8185 |
| Precision | 0.8116 |
| Recall | 0.7619 |
| F1 Score | 0.7860 |
| ROC-AUC | 0.8841 |

---

# Important Predictors

Key churn indicators identified by the model include:

- Loyalty status
- Acquisition channel
- Marketing consent
- Product preferences
- Engagement behavior
- Customer activity patterns

---

# Intended Use

Recommended uses:

- Retention campaign targeting
- Customer risk monitoring
- CRM prioritization
- Marketing intervention planning

---

# Limitations

The model should not be used:

- as the sole decision-making system,
- for customer eligibility decisions,
- without periodic retraining,
- without monitoring feature drift.

---

# Monitoring Recommendations

Monitor:

- ROC-AUC
- Recall
- Churn Rate
- Risk Score Distribution
- Feature Drift

Model performance should be reviewed periodically and retrained when degradation is detected.

---

# Final Recommendation

The Logistic Regression model provides strong predictive performance while remaining transparent and easy to operationalize. The model should be integrated into retention workflows to identify high-risk customers and support proactive customer engagement strategies.