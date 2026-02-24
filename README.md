# Fraud-Detection-Risk-Modeling

## Project Overview

Financial fraud detection is a high-impact machine learning problem due to severe class imbalance and business risk trade-offs.

This project analyzes 284,000+ transaction records to build and evaluate fraud detection models while prioritizing precision–recall performance over raw accuracy.

The objective is to detect fraudulent transactions effectively while minimizing false positives that increase investigation costs.

---

## Dataset

- Source: Credit Card Fraud Detection Dataset (ULB)
- Transactions: 284,807
- Fraud Cases: 492 (~0.17%)
- Features:
  - V1–V28 (PCA-transformed features)
  - Time
  - Amount
  - Class (Target variable: 1 = Fraud, 0 = Legitimate)

*Dataset not included in repository due to size.*

---

## Key Challenges

- Extreme class imbalance
- Fraud cases represent less than 1% of data
- Accuracy is not a reliable metric
- Business cost of false negatives vs false positives

---

## Approach

### 1. Data Preparation
- Stratified train-test split
- Feature scaling for `Time` and `Amount`
- Class imbalance handling using class weights

---

### 2. Baseline Model — Logistic Regression

- Used `class_weight="balanced"`
- Evaluated using:
  - Precision
  - Recall
  - ROC-AUC
  - PR-AUC

Logistic regression provided a strong baseline with interpretable decision boundaries.

---

### 3. Advanced Model — Random Forest

- Implemented ensemble learning
- Handled non-linear relationships
- Extracted feature importance
- Performed threshold tuning for recall optimization

Random Forest demonstrated improved precision-recall balance compared to the baseline model.

---

## Model Evaluation

Models were evaluated using:

- ROC Curve
- Precision-Recall Curve
- Confusion Matrix
- ROC-AUC Score
- PR-AUC Score

Given the severe imbalance, **PR-AUC was prioritized over accuracy.**

---

## Business Interpretation

In fraud detection systems:

- False Negatives (missed fraud) lead to financial loss.
- False Positives increase operational investigation costs.

By adjusting probability thresholds, the system can be tuned depending on business risk appetite.

The Random Forest model offered better recall-precision balance, making it suitable for high-risk transaction environments.

---

## Tools & Technologies

- Python
- Pandas & NumPy
- Scikit-learn
- Matplotlib & Seaborn
- Jupyter Notebook
- 
---

## Key Takeaways

This project demonstrates:

- Handling extreme class imbalance
- Building and comparing classification models
- Evaluating models using precision-recall metrics
- Applying threshold tuning
- Framing machine learning results in business context
