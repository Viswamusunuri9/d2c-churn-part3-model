# Error Analysis Report

## D2C Customer Churn Intelligence Project
### Part 3 - Churn Prediction Modeling

---

# Objective

The purpose of this report is to analyze model prediction errors and identify opportunities for future improvement.

---

# Model Evaluated

Selected Model:

```text
Logistic Regression
```

Validation ROC-AUC:

```text
0.8841
```

---

# Error Types

## False Positives

Definition:

Customer predicted to churn but actually retained.

### Business Impact

- Unnecessary retention incentives
- Additional marketing costs
- Reduced campaign efficiency

### Risk Level

Moderate

False positives typically result in financial inefficiency rather than customer loss.

---

## False Negatives

Definition:

Customer predicted to remain active but actually churned.

### Business Impact

- Lost customers
- Lost revenue
- Missed retention opportunities

### Risk Level

High

False negatives are generally more costly than false positives in churn prediction.

---

# Observed Model Behavior

The model achieved:

- Strong overall discrimination capability
- Balanced precision and recall
- Limited evidence of severe overfitting

The selected model demonstrated stable performance across both customer classes.

---

# Potential Sources of Error

## Behavioral Changes

Customers may alter purchasing behavior rapidly after the snapshot date.

Examples:

- sudden disengagement,
- competitive switching,
- seasonal behavior changes.

---

## Unobserved Variables

The model does not directly observe:

- competitor promotions,
- economic conditions,
- product availability issues,
- external market events.

---

## Data Quality Limitations

Potential issues include:

- incomplete customer information,
- delayed transaction updates,
- changing customer preferences.

---

# Opportunities for Improvement

Future versions of the model may benefit from:

- additional behavioral features,
- time-series features,
- campaign response history,
- customer satisfaction indicators,
- advanced ensemble models.

---

# Recommended Monitoring

Track:

- prediction drift,
- feature drift,
- recall,
- ROC-AUC,
- retention campaign outcomes.

---

# Final Assessment

The model demonstrates strong predictive capability and provides a reliable foundation for churn risk identification. While prediction errors remain unavoidable, the model's performance is sufficient for operational retention planning and customer prioritization.