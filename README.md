# 🚀 Fraud Detection System using Machine Learning

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/Seaborn-0C4B33?style=for-the-badge&logo=python&logoColor=white" />
</p>
.

## 📌 Fraud Detection Model – Imbalanced Financial Data

This project builds a high-performance fraud detection system on extremely imbalanced transaction data:
Fraud ≈ 0.13%
Non-Fraud ≈ 99.87%
Due to class imbalance, accuracy was avoided. The model was optimized for:
Precision
Business trade-offs (fraud capture vs false alarms)
Confusion Matrix

## 🔬 Approach

1️⃣ Exploratory Data Analysis

Distribution analysis

Correlation heatmaps

Class imbalance assessment

Transaction pattern insights

2️⃣ Baseline Model

LogisticRegression(class_weight='balanced')

Feature scaling

Evaluated using Precision & Recall

3️⃣ Threshold Optimization

Tuned decision threshold instead of default 0.5

Reduced False Positives while maintaining high Recall

4️⃣ Model Upgrade – XGBoost

XGBClassifier(scale_pos_weight=ratio)

Handled nonlinear fraud patterns

Improved ranking and class imbalance handling

## Performance Improvements

✅ 93% reduction in False Positives

✅ 12× increase in Precision (~2% → ~25%)

✅ Recall ≈ 99.5%

✅ Improved PR-AUC (~0.54+)

## 💼 Business Impact

With ~25% precision:

If 1,000 transactions are flagged → ~250 are actual fraud

This significantly reduces investigation cost while maintaining near-total fraud capture.

## 🚀 Future Improvements

Hyperparameter tuning

Stratified cross-validation

SHAP explainability

Feature engineering

API deployment for real-time scoring

## 📁 Repository Structure
```
├── Fraud_Detection.ipynb
├── README.md
└── fraud_detection_pipeline.pkl
```
