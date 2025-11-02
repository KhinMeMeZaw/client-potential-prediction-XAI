# Client Potential Prediction using Machine Learning and Explainable AI

This repository contains my Master’s research project — developing a **multi-class classification model** to predict client potential levels (High, Medium, Low, None) in **B2B IT sales** using **machine learning** and **Explainable AI (XAI)** techniques.

---

## Project Overview
In B2B IT solution sales, the sales cycle is long and complex. Sales teams often struggle to identify which leads have the highest potential to convert.  
This project applies **data-driven machine learning** methods to score and classify client potential, enabling better sales prioritization and resource allocation.

The project integrates **Explainable AI (XAI)** techniques to make the model transparent and interpretable for business users.

---

##  Research Objectives
1. Build a **supervised ML model** to predict client potential levels.  
2. Identify which features most influence the model’s predictions.  
3. Provide **interpretable, explainable insights** to support data-driven sales strategies.

---

## Dataset Overview
| Attribute Type | Features | Examples |
|----------------|-----------|-----------|
| Non-Ordinal | Company Size, Required Service, Quotation Type, Meeting Type, Contact Person Role | “SME”, “Corporate”, “NGO” |
| Ordinal | Engagement Level, Urgency Level | “Low”, “Medium”, “High” |
| Numerical | Budget in USD | 5000, 15000 |
| Target | Potential Label | “High”, “Medium”, “Low”, “None” |

 **Dataset size:** 700 records, 14 features  
**Dataset privacy:** Due to company confidentiality, the dataset is not shared.  

---

## Methodology

### Step 1: Data Preprocessing
- Cleaned column names and handled missing values (mean imputation).  
- Applied:
  - **One-Hot Encoding** for categorical variables  
  - **Ordinal Encoding** for Engagement and Urgency levels  
  - **Min-Max Scaling** for normalization  
- Addressed class imbalance using **SMOTE** and **ADASYN** for comparison.  

### Step 2: Model Training
Tested several algorithms:
- Random Forest  
- XGBoost  
- LightGBM  
- Gradient Boosting  
- Decision Tree  
- SVM  
- KNN  
- Logistic Regression  

 **Best Models:**  
- Gradient Boosting: 0.747 accuracy  
- LightGBM: 0.743 accuracy  
- Random Forest: 0.742 accuracy  
(using 10-Fold Cross Validation)

### Step 3: Explainable AI (XAI)
Applied XAI methods for global and local model explainability:
- **Feature Importance** (from top 3 models)  
- **LIME** – Local Interpretable Model-Agnostic Explanations  
- **SHAP** – Shapley Additive Explanations  
- **PDP & ICE** – Partial Dependence and Individual Conditional Expectation plots  

---

##  Key Findings
| Feature | Insight |
|----------|----------|
| **Budget in USD** | Strong positive correlation (r = 0.675) with client potential |
| **Engagement Level** | Higher engagement → higher potential |
| **Urgency Level** | High urgency → higher likelihood of conversion |
| **Required Service** | “Website” and “Other IT services” have highest high-potential clients |
| **Contact Person Role** | CEOs and IT Teams often lead to higher potential |

---

##  Explainability Insights
- **SHAP Summary Plot:** Reveals global influence of features.  
- **LIME Explanation:** Shows why an individual client was classified as low or high potential.  
- **PDP / ICE:** Demonstrates how increasing budget or engagement affects conversion likelihood.  

---

##  Business Insights
- **Budget and engagement** are the strongest conversion indicators.  
- Focus on **SME clients** with medium budgets and strong engagement.  
- Prioritize **high-urgency** leads for quicker follow-ups.  
- Strengthen executive-level engagement (CEOs, IT Teams).  

---

##  Tech Stack
- **Languages:** Python  
- **Libraries:** pandas, numpy, scikit-learn, pycaret, shap, lime, matplotlib, seaborn, lightgbm, xgboost  
- **Tools:** Jupyter Notebook, VS Code, GitHub  

---
##  Project Structure
```plaintext
client-potential-prediction-XAI/
│
├── data/                # (Dataset omitted for confidentiality)
├── notebooks/
│    ├── 01_data_preprocessing.ipynb
│    ├── 02_model_training.ipynb
│    ├── 03_model_evaluation.ipynb
│    ├── 04_XAI_analysis.ipynb
├── results/             # Plots and figures
├── models/              # Saved trained models (.pkl)
├── requirements.txt
└── README.md
---


