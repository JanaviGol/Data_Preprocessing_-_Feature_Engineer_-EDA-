# 🚖 Ride-Hailing Demand Forecasting & Data Preprocessing Engine

## 🎯 Project Overview & Main Goal
The primary goal of this project is to build an end-to-end data preprocessing, cleaning, and feature engineering pipeline for ride-hailing analytics. It ingests raw, multi-source data (CSV, JSON, and SQL) and transforms it into a clean, model-ready dataset (`final_prepared_rides_dataset.csv`) designed for predicting ride demand patterns and surge pricing flags.

---

## 🧰 Tools & Technologies Used
* **Programming Language:** Python 3.14
* **Data Manipulation & Ingestion:** `pandas`, `numpy`, `sqlite3`, `json`
* **Machine Learning & Imputation:** `scikit-learn` (`SimpleImputer`, `KNNImputer`, `StandardScaler`, `MinMaxScaler`, `LabelEncoder`, `OrdinalEncoder`)
* **Statistical Processing:** `scipy` (Z-Score & Winsorization)
* **Data Visualization & Profiling:** `matplotlib`, `seaborn`, `sweetviz`

---

## 📋 Step-by-Step Pipeline & Process

1. **Data Ingestion & Setup:**
   * Ingested multi-format raw datasets: `riders.csv`, `trips.json`, and `city_zones.sql`.
   * Performed initial inspection (`.info()`, null counts, duplicate identification).

2. **Data Cleaning:**
   * Imputed missing numeric values using `SimpleImputer(strategy='mean')` and categorical values using `most_frequent`.
   * Applied `KNNImputer` for multivariate trip attributes (`distance_km`, `duration_min`, `fare_amount`).
   * Standardized date formats and stripped invalid zero-distance/negative-fare records.

3. **Outlier Detection & Handling:**
   * Identified extreme fare and distance values using Z-Score ($|Z| > 3$).
   * Bounded duration anomalies using the IQR method.
   * Applied Winsorization to cap top-tier extreme surge fares.

4. **Data Transformation & Feature Encoding:**
   * Extracted time components (`hour`, `day_of_week`, `month`) from datetime features.
   * Encoded categorical attributes using `LabelEncoder`, `pd.get_dummies()`, and `OrdinalEncoder`.
   * Addressed positive skewness using Log ($\log(1+x)$) and Square-Root transformations.

5. **Feature Scaling:**
   * Scaled numerical variables using both `StandardScaler` and `MinMaxScaler` to equalize feature distributions.

6. **Advanced Feature Engineering:**
   * Engineered custom behavioral metrics: `avg_ride_distance`, `avg_ride_fare`, `is_peak_hour`, `days_since_signup`, `ride_cancellation_rate`, and `surge_flag`.

7. **Export & Data Audit:**
   * Merged cleaned relational datasets safely and generated a before-vs-after audit summary.
   * Saved the final ML-ready file as `final_prepared_rides_dataset.csv`.

8. **Automated EDA & Visualization:**
   * Generated an interactive HTML profiling report using `Sweetviz`.
   * Created seaborn trend plots for **Hourly Ride Demand** and **Surge vs Non-Surge Trips**.