# 🛠️ Data Engineering & Advanced EDA Process Portfolio
**Project Workflow & Methodology Documentation**

---

## 🚀 Overview of the Process
Is project mein humne ek complete data pipeline aur analysis workflow build kiya hai. Data ko alag-alag sources se extract karne se lekar, use clean karne, business insights nikalne aur advanced visualizations tak ka poora safar niche diye gaye steps mein divide kiya gaya hai:

---

## 🧱 Key Milestones & Components Used

### 1. 🔌 Multi-Source Data Ingestion (Data Extraction)
Humne real-world scenarios ko replicate karne ke liye data ko kisi ek source se nahi, balki **4 alag-alag tarikon** se fetch aur load kiya:
* 📂 **Flat Files:** `pd.read_csv()` ka use karke structural tabular data load kiya.
* 🌐 **Semi-Structured Data:** `pd.read_json()` ka use karke modern web-data formats ko handle kiya.
* 🗄️ **Relational Databases:** `sqlite3` aur SQL queries (`SELECT *`) ke zariye database connectivity establish ki.
* 📡 **Live Web APIs:** `requests` library ka use karke real-time internet data ko raw JSON se pandas DataFrame mein convert kiya.

### 2. 🛡️ Data Quality Assurance & Preprocessing (Data Cleaning)
Raw data kabhi perfect nahi hota, isliye humne uski health checkup ki:
* **Structural Inspection:** `shape`, `head()`, `tail()`, aur `info()` se data ka framework samjha.
* **Memory Optimization:** Text data type ko `.astype('category')` mein badla taaki processing fast ho.
* **Data Integrity:** `duplicated().sum()` se redundancy check ki.
* **Smart Imputation:** Missing values ko drop karne ke bajaye, outliers se bachne ke liye unhe **Median** (`fillna()`) se fill kiya.

### 3. 📊 Exploratory Data Analysis (EDA) & Statistics
Data ke andar chupe patterns ko mathematical aur statistical tarike se samjha:
* **Shape Analysis:** Age distribution ka jhukaav dekhne ke liye **Skewness** aur **Kurtosis** calculate kiya.
* **Categorical Slicing:** Unique values check karne ke liye `nunique()` aur counts ke liye `value_counts()` ka use kiya.
* **Aggregations:** `groupby()` ka use karke Income aur Credit Limit ke beech ka direct business connection nikala.

### 4. 🎨 Advanced Data Visualization (Storytelling)
Insights ko visually appealing banane ke liye **Matplotlib** aur **Seaborn** ke powerful charts use kiye:
* **Univariate:** `histplot` (with KDE) aur `boxplot` se distribution aur outliers spot kiye.
* **Bivariate:** `countplot`, `barplot`, `violinplot`, aur tenure trends dekhne ke liye **`regplot` (Regression line)** ka use kiya.
* **Multivariate (Advanced):** * **`heatmap`:** Correlation check karne ke liye.
  * **`pairplot`:** Multiple features ka relation ek sath dekhne ke liye.
  * **`Bubble Chart`:** Data ke 4 dimensions (`X`, `Y`, `Hue`, `Size`) ko ek single plot mein fetch kiya.
  * **`FacetGrid`:** Sub-plots ka use karke alag-alag income categories ko side-by-side compare kiya.

---

## 🛠️ Tech Stack & Toolkit Used

| Category | Libraries / Tools Used | Purpose |
| :--- | :--- | :--- |
| **Data Manipulation** | `pandas`, `numpy` | Data loading, cleaning, aggregation, type conversion |
| **Database & API** | `sqlite3`, `requests` | SQL querying, REST API data extraction |
| **Statistical Analysis** | `.skew()`, `.kurt()`, `.corr()` | Checking data shape, mathematical correlations |
| **Data Visualization** | `matplotlib.pyplot`, `seaborn` | Advanced plotting, grid charting, styling |

---

## 💡 Modern Standard Compliance
Humne code ko future-proof banaya hai! Deprecated `pandas-profiling` ki jagah modern **`ydata-profiling`** ka approach update kiya hai, jo Python 3.11+ aur dynamic environments ko fully support karta hai.