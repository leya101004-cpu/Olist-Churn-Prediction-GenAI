# 📊 Olist-Churn-Prediction-GenAI
> **Enterprise Customer Retention & Decision-Support Framework**

## 📌 Project Overview

This project is an end-to-end Machine Learning and Business Intelligence framework designed to predict, explain, and mitigate customer churn for **Olist**, a major Brazilian e-commerce platform.

Rather than stopping at a basic predictive model, this framework introduces a **Cost-Sensitive Profit Matrix** to mathematically optimize marketing budgets and integrates **GenAI Prompt Engineering** to automate hyper-personalized retention strategies based on SHAP root-cause analysis.

## 🚀 Key Business Outcomes (ROI & Validation)

This framework was rigorously tested against a 93k+ customer dataset. By transitioning from a static 50% probability threshold to an optimized **44.6% financial threshold**, the system achieved the following enterprise-grade metrics:

* **💰 Max Simulated Net Profit:** `R$ 1,303,962.49` (Optimized vs. baseline campaign).

* **🎯 Top-Decile Lift Score:** `1.37x`. By targeting just the top 10% highest-risk customers identified by the model, the framework successfully captured **81.0%** of all actual churners.

* **📉 Strategic Recall:** Achieved a **98% Recall** on the minority class (churners) during hyperparameter tuning, ensuring near-zero False Negatives (lost VIPs).

## 🧠 System Architecture

The pipeline consists of 4 distinct analytical engines:

1. **Predictive Engine (XGBoost):** An optimized gradient boosting classifier trained on RFM (Recency, Frequency, Monetary) and behavioral data to output precise churn probabilities.

2. **Financial Engine (Cost-Sensitive Matrix):** Calculates the exact point of diminishing returns for retention campaigns based on a 15% discount cost and an Average Order Value (AOV) of R\$ 158.91.

3. **Explainability Engine (SHAP):** Extracts the top 3 contributing factors for every individual customer's churn risk (e.g., `delivery_days > 14`, `review_score == 1`).

4. **Action Engine (GenAI):** Ingests the SHAP root causes and financial constraints to automatically generate personalized LLM prompts for Customer Success Managers.

## 📂 Repository Structure

```text
├── notebooks/
│   └── olist_churn_framework.ipynb   # Full pipeline (Data Prep -> XGBoost -> SHAP -> ROI)
├── models/
│   └── best_xgb_model_saved.joblib   # Serialized optimal XGBoost model
├── data/
│   └── olist_decision_matrix_saved.csv # Final VIP prioritized dataset (Outputs)
├── assets/
│   └── dashboard_preview.png         # React/Streamlit UI Mockup
└── README.md
```

## ⚙️ Quick Start & Usage

To instantly load the trained model and decision matrix without retraining:

```python
import pandas as pd
import joblib

# 1. Load the prioritized customer matrix
df_decision = pd.read_csv('data/olist_decision_matrix_saved.csv')

# 2. Load the optimized predictive model
model = joblib.load('models/best_xgb_model_saved.joblib')

# 3. View the High-Risk VIP Queue
vips = df_decision[df_decision['priority_matrix'] == 'High-Risk & High-Value VIP']
print(f"Total High-Risk VIPs requiring immediate action: {len(vips)}")
```

## 🔮 Future Work: SaaS Dashboard Integration

The terminal-based Decision Support Dashboard is currently being migrated into a **FastAPI + React** architecture to provide a seamless GUI for Marketing Directors, allowing for 1-click GenAI email dispatch directly from the CRM.