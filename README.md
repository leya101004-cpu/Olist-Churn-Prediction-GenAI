# 📊 Olist-Churn-Prediction-GenAI

> **Enterprise Customer Retention & Decision-Support Framework**

![Dashboard Preview](assets/dashboard_preview.png)

## 📌 Project Overview
This project is an end-to-end Machine Learning and Business Intelligence framework designed to predict, explain, and mitigate customer churn for **Olist**, a major Brazilian e-commerce platform.

Rather than stopping at a basic predictive model, this framework introduces a **Cost-Sensitive Profit Matrix** to mathematically optimize marketing budgets and integrates **GenAI Prompt Engineering** to automate hyper-personalized retention strategies based on **SHAP root-cause analysis**. 

The entire system is deployed via a modern **React + FastAPI** web dashboard.

## 🚀 Key Business Outcomes (ROI & Validation)
This framework was rigorously tested against a 93k+ customer dataset. By transitioning from a static 50% probability threshold to an optimized **44.6% financial threshold**, the system achieved:

* **💰 Max Simulated Net Profit:** `R$ 1,303,962.49` (Optimized vs. baseline campaign).
* **🎯 Top-Decile Lift Score:** `1.37x`. By targeting just the top 10% highest-risk customers, the framework successfully captured **81.0%** of all actual churners.
* **📉 Strategic Recall:** Achieved a **98% Recall** on the minority class (churners) during hyperparameter tuning, ensuring near-zero False Negatives (lost VIPs).

## 🧠 System Architecture
The pipeline consists of 4 distinct analytical engines, served through a modern web stack:

1. **Predictive Engine (XGBoost):** An optimized gradient boosting classifier trained on RFM (Recency, Frequency, Monetary) and behavioral data.
2. **Financial Engine (Cost-Sensitive Matrix):** Calculates the exact point of diminishing returns for retention campaigns based on a 15% discount cost and an Average Order Value (AOV) of R$ 158.91.
3. **Explainability Engine (SHAP):** Extracts the top 3 contributing factors for every individual customer's churn risk.
4. **Action Engine (GenAI):** Ingests SHAP root causes and financial constraints to automatically generate personalized LLM prompts.

## 💻 Tech Stack
* **Frontend:** React.js, Tailwind CSS, Recharts, Lucide Icons, Vite
* **Backend:** Python, FastAPI, Uvicorn
* **Machine Learning:** Scikit-Learn, XGBoost, SHAP, Pandas

## ⚙️ Quick Start & Usage

**1. Start the Python Backend**
```bash
# From the root directory
uvicorn main:app --reload
```
*Runs on http://127.0.0.1:8000*

**2. Start the React Frontend**
```bash
cd frontend
npm install
npm run dev
```
*Runs on http://localhost:5173*
