# GlobalAIHub_ML_Project
# Credit Approval Prediction – Machine Learning Project

## 📌 Overview
This project predicts whether a credit application should be **approved** ("good") or **rejected** ("bad"/"no_record") based on applicants' demographic, financial, and credit history data. The goal is to mitigate risk by identifying high-risk clients early.

---

## 📂 Dataset
Two datasets were merged using the `ID` column:
1. **`application_record.csv`**: Demographic/socio-economic features (e.g., income, education, employment status).
2. **`credit_record.csv`**: Monthly credit history (e.g., payment delays, loan status).

### Key Features:
| Category              | Examples                          |
|-----------------------|-----------------------------------|
| **Demographics**      | Age, Gender, Marital Status      |
| **Financials**        | Income, Property/Car Ownership   |
| **Credit History**    | Payment Status (`Good_Debt`, `Bad_Debt`) |

---

## 🛠️ Methodology

### 1. Data Preprocessing
- **Handling Missing Values**: Dropped rows with null `Occupation` values.
- **Feature Engineering**:
  - Transformed `DAYS_BIRTH` → `Age` (years) and `DAYS_EMPLOYED` → `WorkingYears`.
  - Categorized credit `STATUS` into `Good_Debt` (timely payments) and `Bad_Debt` (delays).
- **Class Imbalance**: Created 3 target classes: `good`, `bad`.

### 2. Addressing Class Imbalance
Used **SMOTE** to oversample minority classes (`bad`), ensuring balanced training data.

### 3. Model Selection
Evaluated three models using **weighted F1-score** (due to imbalance):
1. **Logistic Regression**
2. **K-Nearest Neighbors (KNN)**
3. **Random Forest (Best Performance)**  
   - Optimized hyperparameters with **Optuna** (`n_estimators=171`, `max_depth=30`).

---

## 📊 Results
### Random Forest Performance:
| Metric       | Precision | Recall | F1-Score |
|--------------|-----------|--------|----------|
| **good**     | 0.92      | 0.95   | 0.93     |
| **bad**      | 0.89      | 0.82   | 0.85     |
| **Accuracy** |           |        | **0.89** |

## KAGGLE 
## https://www.kaggle.com/code/selvetelifdemirel/credit-approval-ml-project

### Key Insights:
- **Top Predictive Features**: `TotalIncome`, `Age`, `WorkingYears`.
- **Confusion Matrix**: High accuracy in identifying `good` clients, with moderate performance for `bad` cases.

---

## 🚀 How to Reproduce
1. **Install Dependencies**:
   ```bash
   pip install pandas numpy scikit-learn imbalanced-learn optuna seaborn matplotlib
