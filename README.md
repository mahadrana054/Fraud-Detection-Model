# 🚀 Fraud Detection System using Machine Learning
<p align="center"> <img src="https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python"> <img src="https://img.shields.io/badge/Scikit--Learn-ML-orange?style=for-the-badge&logo=scikitlearn"> <img src="https://img.shields.io/badge/Pandas-Data%20Processing-darkblue?style=for-the-badge&logo=pandas"> <img src="https://img.shields.io/badge/Seaborn-Visualization-teal?style=for-the-badge&logo=python"> <img src="https://img.shields.io/badge/XGBoost-Gradient%20Boosting-green?style=for-the-badge"> </p>
📌 Project Overview

This project focuses on building a high-performance Fraud Detection Model for highly imbalanced financial transaction data.

Fraud detection is a classic real-world machine learning problem where:

Fraud transactions ≈ 0.13%

Non-fraud transactions ≈ 99.87%

Because of extreme imbalance, accuracy is not a reliable metric.
Instead, this project focuses on improving:

🎯 Precision

🔍 Recall

📈 Average Precision Score (APS / PR-AUC)

⚖ Business trade-offs between fraud detection and false alarms

📊 The Initial Challenge
Class Distribution
Class	Percentage
Non-Fraud	99.87%
Fraud	0.13%

This extreme imbalance caused:

Very high accuracy (~94%)

🚨 Extremely low precision (~2%)

❌ Massive false positives (87,158)

Initial Confusion Matrix:

[[1501452   87158]
 [    138    1907]]


Although recall was good, the model was generating too many false alerts.

🔬 Approach & Strategy
1️⃣ Data Exploration & Visualization

Data was thoroughly explored and visualized using:

Distribution plots

Correlation heatmaps

Class imbalance analysis

Transaction pattern insights

Libraries used:

Pandas

Seaborn

Matplotlib

Visualization helped uncover:

Feature relationships

Outlier behavior

Class separation trends

2️⃣ Baseline Model – Logistic Regression

Model:

LogisticRegression(class_weight='balanced')


Improvements:

Feature scaling applied

Class imbalance handled using class_weight

Evaluation moved from Accuracy → Precision/Recall

However, precision remained low due to:

Linear decision boundary

Complex fraud patterns

3️⃣ Threshold Optimization

Instead of using default 0.5 threshold:

y_probs = model.predict_proba(X_test)[:,1]


Different thresholds were tested to:

Reduce False Positives

Improve Precision

Maintain high Recall

This shifted focus from “classification” to probability ranking optimization.

4️⃣ Model Upgrade – XGBoost 🚀

Fraud patterns are rarely linear.

Upgraded to:

XGBClassifier(scale_pos_weight=ratio)


Where:

ratio = non_fraud / fraud


Why XGBoost?

Handles nonlinear relationships

Works well with imbalanced data

Supports class weighting

Strong performance in real-world fraud systems

📈 Final Results
New Confusion Matrix
[[1582475    6135]
 [      9    2036]]

🔥 Performance Metrics
Metric	Before	After
Precision	~2%	~25%
Recall	~93%	~99.5%
False Positives	87,158	6,135
APS (PR-AUC)	~0.54	Improved
🏆 Key Improvements Achieved

✅ 93% reduction in False Positives
✅ 12x increase in Precision
✅ Near-perfect Recall
✅ Strong ranking ability (APS ≈ 0.54+)

This transformed the model from:

High-accuracy but impractical

to:

Operationally efficient and production-oriented

📌 Business Perspective

With improved precision (~25%):

If 1,000 transactions are flagged:

~250 are actual fraud

This significantly reduces investigation cost while maintaining high fraud capture.

🛠 Tech Stack

🐍 Python

📊 Pandas

📈 Seaborn

🤖 Scikit-learn

⚡ XGBoost

📉 Matplotlib

🔬 NumPy

📊 Evaluation Metrics Used

Confusion Matrix

Precision

Recall

F1 Score

ROC-AUC

Average Precision Score (PR-AUC)

Precision-Recall Curve

Threshold Tuning

🧠 Key Learnings

Accuracy is misleading in imbalanced datasets

Precision-Recall curve is critical for rare-event detection

Threshold tuning is often more important than model change

Tree-based ensemble models outperform linear models in fraud detection

Business trade-offs must guide model optimization

🔮 Future Enhancements

Hyperparameter tuning with GridSearchCV

Cross-validation with StratifiedKFold

SHAP for model explainability

Feature engineering (rolling features, transaction frequency)

Deployment via API

Real-time fraud scoring pipeline

📁 Repository Structure
├── Fraud_Detection_Notebook.ipynb
├── README.md
└── requirements.txt

✨ Conclusion

This project demonstrates an end-to-end machine learning workflow:

Data exploration

Model building

Imbalance handling

Threshold optimization

Business-driven evaluation

Model improvement using Gradient Boosting

It reflects practical fraud detection strategies used in industry-grade systems.

📬 Connect

If you found this project insightful, feel free to ⭐ the repository.
