# 🛒 SmartCart Analytics — Customer Purchase Behavior Pipeline
> *"Transforming multi-source retail chaos into clean, model-ready intelligence through end-to-end data preprocessing and feature engineering."*

---

## 📌 Executive Project Summary
**SmartCart Analytics** is an enterprise-grade Data Preprocessing & Feature Engineering pipeline. Raw transactional and demographic data is ingested from **multi-format sources (CSV, JSON, SQL)**, cleaned, imputed, scaled, engineered, and exported into a unified, model-ready dataset (`final_cleaned_dataset.csv`).

---

## 🏗️ End-to-End Pipeline Architecture

```text
[ Multi-Source Ingestion ] ── (CSV, JSON, SQL Databases)
        │
        ▼
 [ Step 1: Data Ingestion & Inspection ] ──> Dtypes, Missing Checks & Structure Overview
        │
        ▼
 [ Step 2: Comprehensive Data Cleaning ] ──> SimpleImputer (Mean/Mode), KNN Imputer & Datetime Fixes
        │
        ▼
 [ Step 3: Advanced Outlier Handling ] ───> IQR Filtering, Z-Score Thresholding & Winsorization
        │
        ▼
 [ Step 4: Data Transformation ] ─────────> Date Decomposition, Label/Ordinal/OHE Encoding & Binning
        │
        ▼
 [ Step 5: Feature Scaling ] ──────────────> StandardScaler (Z-Score) & MinMaxScaler ([0, 1])
        │
        ▼
 [ Step 6: Feature Construction ] ────────> RFM Metrics (Recency, Frequency, Avg Spend, Category Spend)
        │
        ▼
 [ Step 7: Final Dataset Preparation ] ───> Left Join Merge on user_id & Quality Audit
        │
        ▼
 [ Step 8: Auto-EDA & Artifact Export ] ──> Sweetviz HTML Dashboard & Clean CSV Output


 