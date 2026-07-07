# 🩺 Advanced Data Cleansing & Quality Optimization for Healthcare Analytics

---

## 📺 Project Walkthrough Video
> 💡 **Instructor Note:** I have recorded a detailed 10-minute presentation covering every technical step, code block execution, and logical analysis of this engineering project.
* 🔗 **[\[Click Here to Watch the Full Project Presentation Video](https://drive.google.com/drive/home)** 👈 

---

## 📌 Project Objective
Real-world healthcare datasets are often deeply compromised by incomplete testing logs and extreme sensor glitches. The primary objective of this project is to implement an advanced pipeline using **Scikit-Learn** and **SciPy** to treat complex missing data structures and clinical outliers, transforming a corrupted raw file into a **100% complete, Machine Learning-ready dataset** for predicting `disease_risk`.

---

## 📂 Dataset Architecture & Structural Baseline
The raw data ingestion contains **400 rows** and **9 distinct features** documenting patient health parameters:

| Feature Name | Category | Missing Status (Before Cleaning) | Data Integrity Impact |
| :--- | :--- | :--- | :--- |
| **patient_id** | System Log | 0 Missing (100% Clean) | Unique structural identifier. |
| **age** | Demographics | 40 Missing (10.00%) | Distorts chronological risk curves. |
| **gender** | Demographics | 32 Missing (8.00%) | Missing grouping classes. |
| **region** | Demographics | 48 Missing (12.00%) | Highest missing rate in dataset. |
| **bmi** | Clinical Metric | 32 Missing (8.00%) | Vital continuous body mass feature. |
| **blood_pressure** | Clinical Metric | 0 Missing (100% Clean) | Baseline blood pressure log. |
| **cholesterol** | Clinical Metric | 40 Missing (10.00%) | Heavy missing variance. |
| **glucose** | Clinical Metric | 35 Missing (8.75%) | Missing critical metabolic indices. |
| **disease_risk** | Target Variable | 0 Missing (100% Clean) | **Supervised Binary Label (0 or 1)**. |

---

## 🛠️ Step-by-Step Engineering Pipeline

### 🏗️ Phase 1: Ingestion & Missing Data Assessment
* **Step 1: Framework Ingestion:** Initialized environment with core frameworks (`pandas`, `numpy`), visualization stacks (`seaborn`, `matplotlib`), and statistical layers (`scipy.stats`).
* **Step 2 & 3: Stream Configuration & Preview:** Mounted data securely using parent-directory referencing (`../Datasets/patient_health_records.csv`) to protect absolute workspace integrity.
* **Step 4: Density Assessment:** Ran matrix null analytics (`df.isnull().sum()`) to compute the exact missing counts and percentage weights shown in the summary table above.

### 🧮 Phase 2: Advanced Data Imputation Strategies
* **Step 5: Mean Imputation:** Used baseline `SimpleImputer(strategy='mean')` on `bmi` to map default averages into blank coordinates without modifying overall variance.
* **Step 6: Mode Imputation (Categorical Data):** Deployed `SimpleImputer(strategy='most_frequent')` to resolve gaps in string features (`gender` and `region`), preserving native categorical class frequencies.
* **Step 7: Missing Indicator & Random Sampling:** Created a binary tracking feature `age_isna` to record structural absence before filling `age` missing slots via random historical samplings, preserving original distribution curves perfectly.
* **Step 8: KNN Multivariate Imputation:** Dropped basic averages and used spatial geometry via `KNNImputer(n_neighbors=3)` to compute neighbor distance metrics across continuous parameters, reducing `cholesterol` null fields to 0.
* **Step 9: MICE Algorithm:** Used chained equation structures via `IterativeImputer` to completely clear multi-dimensional dependencies in `glucose`, bringing overall missing records across the framework down to **absolute zero**.

### 📏 Phase 3: Outlier Engineering & Threshold Tuning
* **Step 10: Z-Score Trimming:** Evaluated extreme deviations on `cholesterol` and `glucose`. Row deletion via standard $|Z| > 3$ bounds identified 16 outliers but shrunk operational capacity down to 368 records.
* **Step 11: Interquartile Range (IQR) Trimming:** Filtered structural boundaries on `bmi` using the statistical formula ($IQR = Q3 - Q1$), locating 19 out-of-boundary patient records.
* **Step 12: Percentile Capping:** Changed strategies to stop data loss by using `np.clip` to securely lock `bmi` variances inside strict 1st and 99th percentile limits.
* **Step 13: Multivariate Winsorization:** Executed systematic `winsorize(limits=[0.05, 0.05])` across numerical profiles (`blood_pressure`, `bmi`, `cholesterol`, `glucose`). This capped extreme outliers at 5% boundaries, neutralizing distortions while **preserving all 400 patient profiles**.

### 💾 Phase 4: Output Deployment & Verification
* **Step 14: Data Export:** Transferred clean parameters into target storage as `final_cleaned_patient_records.csv` with row tracking flags suppressed (`index=False`).
* **Step 15: Structural Boundary Audit:** Verified system metrics to guarantee zero outstanding missing rows while checking safe boundary conditions (e.g., maximum BMI successfully locked at 34.85).

---

## 📊 Core Analytical Findings (Project Report)

### 1. Which Imputation Strategy Was Most Effective?
**Answer:** For clinical data tracking (`bmi`, `cholesterol`, `glucose`), multivariate approaches like **MICE (IterativeImputer)** and **KNN Imputer** were far more effective than simple defaults. Instead of dropping flat averages that distort graphs, they look at neighboring health features to estimate logical values. For string values (`gender`, `region`), **Most Frequent (Mode) Imputation** worked perfectly to maintain natural background distributions.

### 2. Which Outlier Handling Method Preserved Data Quality Best?
**Answer:** **Winsorization (Capping)** preserved overall dataset quality best. While Z-Score and IQR methods successfully drop extreme anomalies, they delete raw rows entirely, reducing our asset size from 400 rows to 368 rows. Winsorization keeps 100% of the patient profiles active by gently pulling extreme values back to the 5th and 95th percentile boundaries.

### 3. How Data Cleaning Improved Dataset Usability?
**Answer:** Raw medical inputs are filled with missing gaps and extreme measurement spikes that break standard Machine Learning models or cause wrong predictions. This data preprocessing pipeline resolved every flaw, established a clean baseline, minimized data loss, and successfully established a **100% complete, highly optimized, Machine Learning-ready dataset** built for high-accuracy predictive tasks.