# 🏥 Medicare Claims Anomaly Detection & Billing Fraud Intelligence

> An end-to-end anomaly detection pipeline built on 1M+ Medicare claims records using Isolation Forest and ensemble models to identify billing fraud with 98% accuracy, with PII-compliant data governance and interpretable fraud predictors surfaced via feature importance analysis.

---

## 📌 Overview

Investigated **1M+ Medicare claims records** (reduced to 250K via feature-engineered subset) using **Isolation Forest** and **ensemble models** to detect billing anomalies with **98% accuracy**. Integrated **Logistic Regression** and **Random Forest** feature importance analysis to surface key fraud predictors for stakeholder reporting, all while enforcing **PII-compliant data governance** across sensitive healthcare records.

---

## 🚀 Key Features

- **Anomaly Detection at Scale** — Isolation Forest trained on 1M+ CMS Medicare Part D claims to flag suspicious billing patterns
- **Ensemble Modeling** — combined multiple classifiers to optimize fraud detection accuracy to 98%
- **Feature Importance Analysis** — Logistic Regression and Random Forest used to rank and surface top fraud predictors for stakeholders
- **PII-Compliant Data Governance** — de-identification and governance controls applied across all patient and provider records
- **Fraud Pattern Coverage** — detects service provider fraud, duplicate billing, opioid prescription abuse, and geo-demographic anomalies

---

## 🏗️ Pipeline Architecture

```
CMS Medicare Claims Data (1M+ records)
        │
        ▼
  Data Preprocessing & Governance
  (PII Removal, De-identification,
   Feature Engineering, Sampling → 250K)
        │
        ▼
Anomaly Detection Layer
  ├── Isolation Forest (unsupervised)
  └── Ensemble Models (boosting + voting)
        │
        ▼
Predictive Analytics Layer
  ├── Logistic Regression
  └── Random Forest
        │
        ▼
Feature Importance Analysis
  (Top Fraud Predictors for Stakeholders)
        │
        ▼
Evaluation & Reporting
  (Accuracy: 98% | AUC-ROC | Confusion Matrix)
```


## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| Anomaly Detection | Isolation Forest (scikit-learn) |
| Classification | Logistic Regression, Random Forest, Ensemble |
| Data Processing | Python, Pandas, PySpark |
| Governance | PII de-identification, HIPAA-aligned controls |
| Evaluation | AUC-ROC, Accuracy, Confusion Matrix |
| Language | Python 3.9+ |

---

## 📊 Dataset

- **Source:** [CMS Medicare Part D Prescriber Data](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Part-D-Prescriber.html)
- **Size:** 1M+ records → 250K engineered feature subset
- **Key Features Used:**
  - Number of procedures/services per provider (NPI)
  - Average charges submitted vs. actual payments received
  - Prescription patterns (opioid %, brand-name %, Schedule II/III drugs)
  - Geo-demographic provider attributes
  - LEIE exclusion labels (mapped fraud ground truth)


## 💡 Fraud Patterns Detected

| Fraud Type | Detection Method |
|---|---|
| Duplicate / overbilling | Isolation Forest on charge vs. payment delta |
| Opioid prescription abuse | Drug pattern features (Schedule II/III %) |
| Excluded provider billing | LEIE label mapping via NPI |
| Geo-demographic hotspots | Regional clustering + anomaly scoring |
| High-volume low-complexity billing | Ensemble classifier on procedure patterns |

---

## 🔒 Data Governance

All records processed under PII-compliant governance controls:
- Patient and provider identifiers de-identified prior to modeling
- Analysis conducted exclusively on publicly available CMS open data
- No protected health information (PHI) stored or transmitted

---

## 🔭 Future Work

- Integrate **graph-based fraud detection** to surface provider collusion networks
- Add **SHAP explainability** for model-level fraud attribution per claim
- Scale pipeline to full 3GB+ CMS dataset using **PySpark distributed processing**
- Deploy real-time scoring API for live claims adjudication workflows

---

## 👤 Author

**Nithin Kumar**
📧 nithink12131@gmail.com | [nithinkumar.vercel.app](https://nithinkumar.vercel.app)
