# 💳 Customer Credit Risk Assessment & Data Preprocessing Pipeline

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

An end-to-end Machine Learning data preprocessing pipeline built to clean, impute, transform, and scale customer financial records for accurate **Credit Risk Modeling**.

---

## 📌 Project Overview

In credit risk evaluation, raw financial datasets often contain missing values, inconsistent formats, unscaled metrics, and outliers. This project builds a robust **8-Part Preprocessing Pipeline (Parts A–H)** that transforms raw, noisy multi-source customer data into a ML-ready structured dataset (`final_customer_credit_risk_cleaned.csv`).

### 🎯 Key Objectives:
- **Multi-Source Integration:** Load and merge CSV transactions, JSON metadata, SQL repayment records, and API indicators.
- **Advanced Imputation:** Handle missing data dynamically using **MICE (`IterativeImputer`)** and **KNN Imputer**.
- **Outlier Mitigation:** Detect outliers using IQR/Z-Score and cap them using **Winsorization**.
- **Feature Engineering & Construction:** Construct financial ratios like **Debt-to-Income (DTI)** and **Spending-to-Income**.
- **Scaling & Normalization:** Apply **RobustScaler**, **StandardScaler**, and **PowerTransformer** (Box-Cox / Yeo-Johnson).

---

## 🎥 Video Explanation & Walkthrough

Watch the complete project breakdown and step-by-step code demonstration:

[![Watch Project Explanation](https://img.youtube.com/vi/YOUR_VIDEO_ID/maxresdefault.jpg)](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)

## 🛠️ Tech Stack & Dependencies

- **Language:** Python 3.9+
- **Data Manipulation:** `pandas`, `numpy`
- **Machine Learning & Preprocessing:** `scikit-learn`, `scipy`
- **Missing Value Imputation:** `fancyimpute` / `sklearn.impute`
- **Environment:** Jupyter Notebook / VS Code

---

## 👤 Author : Janavi Gol

✨ Thank you for visiting this repository! ✨

If you found this project helpful, feel free to give it a ⭐ star!


## 📂 Repository Structure

```text
├── data/
│   ├── raw_transactions.csv
│   ├── customer_metadata.json
│   └── final_customer_credit_risk_cleaned.csv   # Final Cleaned Output
├── docs/
│   └── Customer_Credit_Risk_Theory_Document.pdf # Comprehensive Theory Documentation
├── Customer_Credit_Risk_Pipeline.ipynb           # Executed Jupyter Notebook
├── README.md                                     # Project Documentation
└── requirements.txt                              # Project Dependencies

