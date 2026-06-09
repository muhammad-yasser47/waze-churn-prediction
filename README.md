# Waze User Churn Prediction 

<img width="409" height="529" alt="image" src="https://github.com/user-attachments/assets/a7551040-6fa3-45e3-a692-393349e4c38a" />


**Overview**

This project develops an end-to-end machine learning solution to predict user churn for Waze using behavioral and engagement data. The goal is to identify users who are likely to stop using the platform so that retention strategies can be implemented proactively.

**Business Problem**

Customer retention is a critical challenge for navigation platforms such as Waze. The objective was to identify users at risk of churn, understand behavioral patterns, and build predictive models to support retention efforts.

**Dataset**
- Approximately 15,000 Waze users
- User activity features: sessions, drives, activity days, driving days, total sessions, kilometers driven, duration driven
- User attributes: device type, days since onboarding
- Target variable: retained vs churned

**Project Workflow**
1. Data Preparation
- Loaded data from Spark into Databricks
- Investigated missing values and outliers
- Removed rows with missing target labels

2. Exploratory Data Analysis
- Churned users drove longer distances but used the app less consistently
- Retained users showed higher engagement levels
- Long-distance drivers exhibited higher churn tendencies

<img width="1000" height="462" alt="image" src="https://github.com/user-attachments/assets/93413c2c-8a33-417e-9ee7-2dcda95750ac" />


3. Feature Engineering
- km_per_driving_day
- km_per_drive
- total_sessions_per_day
- km_per_hour
- professional_driver flag

4. Hypothesis Testing
Research Question:
Do iPhone and Android users have different average numbers of drives?

Method:
Welch's Two-Sample T-Test

Result: p-value = 0.244

No statistically significant difference between device types.


**Machine Learning Models**

Logistic Regression
Accuracy: 82%
Precision: 52%
Recall: 9%
F1 Score: 16%

Random Forest
Accuracy: 81.9%
Precision: 45.7%
Recall: 12.7%
F1 Score: 19.8%

XGBoost (Champion Model)
Best Parameters:
learning_rate = 0.1
max_depth = 12
min_child_weight = 5
n_estimators = 300

Final Test Performance:
Accuracy: 80.8%
Precision: 41.6%
Recall: 20.1%
F1 Score: 27.1%

<img width="350" height="168" alt="image" src="https://github.com/user-attachments/assets/0703fadd-d912-41d3-8274-14b82e408e9b" />


**Model Selection**

Recall was selected as the primary evaluation metric because the dataset was imbalanced (82% retained vs 18% churned). Missing churned users was considered more costly than incorrectly flagging retained users.

<img width="562" height="426" alt="image" src="https://github.com/user-attachments/assets/57d51cec-887d-4654-b8ce-5c8eafec7491" />


**Key Insights**

- km_per_hour has the highest importance score (~1585)
- Professional drivers had substantially lower churn rates.
- Long-distance drivers were more likely to churn.

<img width="765" height="446" alt="image" src="https://github.com/user-attachments/assets/6fdb9430-f691-4a1c-a1bb-54d6783a578f" />


**Technologies Used**

Databricks, Apache Spark, Python, Pandas, NumPy, Matplotlib, Scikit-learn, XGBoost

**Skills Demonstrated**

EDA, Statistical Testing, Feature Engineering, Machine Learning, Classification Modeling, Hyperparameter Tuning, Model Evaluation, Customer Analytics

**Future Improvements**

- SMOTE and class balancing
- SHAP explainability
- Threshold optimization
- Ensemble methods
- Production deployment

**Conclusion**

This project demonstrates a complete machine learning workflow for customer churn prediction, from data exploration and feature engineering to model development and evaluation.
