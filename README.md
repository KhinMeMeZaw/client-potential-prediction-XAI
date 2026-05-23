#  Client Potential Prediction using Machine Learning & Explainable AI

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![PyCaret](https://img.shields.io/badge/PyCaret-3.x-orange)
![SHAP](https://img.shields.io/badge/XAI-SHAP%20%7C%20LIME%20%7C%20PDP%20%7C%20ICE-green)
![Status](https://img.shields.io/badge/Status-MSc%20Thesis%20In%20Progress-yellow)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

> **MSc Thesis Project** — Mae Fah Luang University, Digital Transformation Technology (2024–Present)  
> **Author:** Khin Me Me Zaw | [LinkedIn](https://www.linkedin.com/in/khin-me-me-zaw-a8356317b/) | [GitHub](https://github.com/KhinMeMeZaw)

---

##  Project Summary

In B2B IT sales, identifying which leads have the highest conversion potential is costly and time-consuming. Sales teams often rely on intuition, leading to missed opportunities and wasted resources.

This project builds a **multi-class classification model** that predicts client potential levels — **High, Medium, Low, or None** — using real CRM and sales data from a B2B IT company. It combines machine learning with **Explainable AI (XAI)** methods so that predictions are not just accurate, but **interpretable and actionable** for business decision-makers.

**Why this matters:**
- Sales teams can prioritize high-potential leads faster
- Managers get data-backed justification for resource allocation
- XAI outputs translate model decisions into plain business language

---

## Project Structure

```
client-potential-prediction-XAI/
│
├── data/                          # Dataset (omitted — company confidential)
├── notebooks/
│   ├── 01_data_preprocessing.ipynb    # Cleaning, encoding, scaling, SMOTE/ADASYN
│   ├── 02_model_training.ipynb        # PyCaret AutoML + manual tuning
│   ├── 03_model_evaluation.ipynb      # Cross-validation, confusion matrix, metrics
│   └── 04_XAI_analysis.ipynb          # SHAP, LIME, PDP, ICE explanations
├── models/                        # Saved .pkl model files
├── results/                       # Charts, plots, XAI outputs
├── presentation/                  # Thesis slides
├── references/                    # Research papers & citations
└── README.md
```

---

## Dataset

| Attribute | Details |
|---|---|
| Records | 700 client interactions |
| Features | 14 (categorical, ordinal, numerical) |
| Target | Client Potential: `High` / `Medium` / `Low` / `None` |
| Source | Real B2B IT company CRM data (anonymized) |

**Key features used:**

| Type | Features |
|---|---|
| Categorical | Company Size, Required Service, Quotation Type, Meeting Type, Contact Person Role |
| Ordinal | Engagement Level, Urgency Level |
| Numerical | Budget (USD) |

> Raw dataset not included due to company confidentiality agreement.

---

##  Methodology

### Pipeline Overview

```
Raw CRM Data
    │
    ▼
Data Cleaning & Preprocessing
(Missing values → One-Hot / Ordinal Encoding → Min-Max Scaling)
    │
    ▼
Class Imbalance Handling
(SMOTE vs ADASYN — compared for best performance)
    │
    ▼
Model Training & Comparison (PyCaret AutoML)
(Random Forest · LightGBM · Gradient Boosting · XGBoost · SVM · KNN · LR)
    │
    ▼
10-Fold Cross Validation + Hyperparameter Tuning
    │
    ▼
Explainable AI (XAI) Analysis
(Feature Importance · SHAP · LIME · PDP · ICE)
    │
    ▼
Business Insights & Recommendations
```

---

##  Model Results

| Model | Accuracy | Notes |
|---|---|---|
| **Gradient Boosting** | **74.7%** | Best overall |
| LightGBM | 74.3% | Best speed/accuracy trade-off |
| Random Forest | 74.2% | Most interpretable baseline |
| XGBoost | ~73% | Strong but slower |
| Others (SVM, KNN, LR) | < 70% | Less suitable for this data |

> Evaluation: 10-Fold Stratified Cross Validation | Metrics: Accuracy, F1-Score, Precision, Recall

---

##  Explainable AI (XAI) Results

| Method | Scope | Key Output |
|---|---|---|
| **Feature Importance** | Global | Top features ranked by model weight |
| **SHAP** | Global + Local | How each feature pushes prediction up or down |
| **LIME** | Local | Why *this specific client* got classified as High/Low |
| **PDP** | Global | How budget or engagement level affects outcome across all clients |
| **ICE** | Local | How the relationship varies per individual client |

---

##  Key Business Insights

| Finding | Business Action |
|---|---|
| **Budget** is the #1 predictor (r = 0.675 with potential) | Focus prospecting on clients with adequate budget signals |
| **Engagement Level** strongly predicts conversion | Invest in nurturing medium-engagement leads before they go cold |
| **Urgency Level** correlates with faster sales cycles | Prioritize high-urgency leads for immediate follow-up |
| **Contact Person Role** matters — CEOs & IT Leads convert best | Target decision-makers, not just coordinators |
| **Website & IT Services** clients have highest High-potential rate | Tailor pitches for these service categories |

---

##  Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3.10 |
| ML Framework | PyCaret, Scikit-learn |
| Algorithms | LightGBM, XGBoost, Gradient Boosting, Random Forest |
| XAI | SHAP, LIME, PDPbox |
| Imbalance Handling | imbalanced-learn (SMOTE, ADASYN) |
| Visualization | Matplotlib, Seaborn |
| Environment | Google Colab, Jupyter Notebook |
| Version Control | Git, GitHub |

---

##  How to Run

```bash
# 1. Clone the repo
git clone https://github.com/KhinMeMeZaw/client-potential-prediction-XAI.git
cd client-potential-prediction-XAI

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open notebooks in order
# Start with: notebooks/01_data_preprocessing.ipynb
```

> Note: The original dataset is confidential. You can substitute any B2B CRM-style dataset with similar feature types to replicate the workflow.

---

##  About the Author

**Khin Me Me Zaw**
- MSc Digital Transformation Technology, Mae Fah Luang University (2024–Present)
- B.C.Sc Business Information Systems, University of Information Technology (2014–2019)
- Google Data Analytics & Google AI Essentials Certified
- 3+ years experience in data analysis and business development

📧 kmezaw1998@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/khin-me-me-zaw-a8356317b/) | [GitHub](https://github.com/KhinMeMeZaw)

---

*This project is part of an MSc thesis. All business data has been anonymized. Research conducted under academic supervision at Mae Fah Luang University.*
