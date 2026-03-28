# 📊 Customer Churn Analysis: Predicting & Preventing Customer Loss

## 📌 Overview
This project analyzes customer data to understand churn behavior and build machine learning models capable of identifying customers at risk of leaving. The goal is to provide data-driven insights that support retention strategies and reduce revenue loss through targeted intervention campaigns.

## 🎯 Objectives
- Analyze customer demographics and behavioral patterns
- Identify key factors that drive customer churn
- Build and compare multiple classification models
- Evaluate model profitability using real-world business assumptions
- Provide actionable recommendations to reduce churn

## 📂 Dataset
The dataset contains customer-level information sourced from Kaggle, including:
- Customer ID & Demographics (Age, Gender)
- Subscription Type & Contract Length
- Usage metrics (Support Calls, Payment Delay)
- Churn label (target variable)

> **Source:** [Customer Churn Dataset — Kaggle](https://www.kaggle.com/datasets/muhammadshahidazeem/customer-churn-dataset)

## 🛠️ Tools & Technologies
- Python
- Pandas
- NumPy
- Matplotlib / Seaborn
- Scikit-learn
- Google Colab

## 🔍 Key Analysis Steps

### 1. Data Exploration
- Reviewed dataset shape, data types, and missing values
- Examined class distribution (churn vs. non-churn)
- Identified categorical and numerical feature groups

### 2. Exploratory Data Analysis (EDA)
- Categorical variables vs. Churn (Gender, Subscription Type, Contract Length)
- Numerical variables vs. Churn (boxplots and distribution analysis)
- Correlation heatmap across all numerical features and target variable
- Extracted churn rate per group with actionable insights

### 3. Feature Engineering
- Dropped non-informative ID column
- Applied **One-Hot Encoding** on nominal categorical variables (Gender, Subscription Type, Contract Length) — no ordinal relationship assumed
- Applied **Train-Test Split** (80:20) with `stratify=y` to preserve class balance and avoid data leakage
- Applied **StandardScaler** fitted on training data only — prevents leakage to test set

### 4. Modelling
Trained and evaluated 4 classification models with `class_weight='balanced'` to handle class imbalance:

| Model | Notes |
|---|---|
| Logistic Regression | Baseline linear model |
| K-Nearest Neighbors (KNN) | Distance-based, no class weighting |
| Decision Tree | Tree-based, interpretable |
| SVM RBF | Kernel-based, non-linear boundaries |

### 5. Model Evaluation
- Metrics: Accuracy, Precision, Recall, F1-Score (on train & test sets)
- Primary focus: **Recall** — minimizing False Negatives (missed churners)
- Generalization assessed via train-test metric gap

### 6. Profitability Analysis
Business assumptions used:

| Parameter | Value |
|---|---|
| Customer Lifetime Value (CLV) | $1,200 |
| Retention Campaign Cost | $50/customer |
| Retention Success Rate | 30% |

Each model was evaluated on Net Profit, Total Savings, and ROI from applying its predictions to real campaign targeting.

## 📊 Key Insights
- **Support Calls** is the strongest churn predictor — customers with more complaints are significantly more likely to leave
- **Payment Delay** shows a clear positive correlation with churn risk
- Customers on **month-to-month contracts** churn at much higher rates than long-term contract holders
- **Subscription type** influences churn rate — premium subscribers tend to stay longer
- Heavy discounters and short-tenure customers show elevated risk profiles

## 📈 Business Recommendations
- Proactively monitor customers with high support call frequency as early churn signals
- Implement automated follow-ups after repeated complaints to reduce friction
- Offer contract upgrade incentives to month-to-month customers
- Prioritize retention campaigns on customers with payment delays before they escalate
- Use the best-performing model to score customer base monthly and trigger targeted outreach

## 📸 Visualizations


## 🚀 Future Improvements
- Apply SMOTE or resampling techniques to handle class imbalance more explicitly
- Tune hyperparameters with GridSearchCV for each model
- Add ensemble methods (Random Forest, XGBoost)
- Build an interactive churn prediction dashboard (Streamlit or Power BI)
- Implement time-based cohort analysis to track churn over customer lifecycle

## 👤 Author
**Syaibatul Hamdi** — Data Consultant based in France

---
⭐ Feel free to explore and give feedback!
