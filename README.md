# Credit Card Approval ML Project

This repository hosts a Jupyter Notebook (`credit-approval-ml-project.ipynb`) that predicts credit card application approvals using machine learning.
### Kaggle: https://www.kaggle.com/code/selvetelifdemirel/credit-approval-ml-project
## 📋 Table of Contents

- [🔍 Project Description](#project-description)
- [📂 Dataset](#dataset)
- [⚙️ Prerequisites](#prerequisites)
- [🚀 Installation](#installation)
- [▶️ Usage](#usage)
- [📝 Notebook Structure](#notebook-structure)
- [📊 Results Summary](#results-summary)
- [🤝 Contributing](#contributing)

## 🔍 Project Description

This project classifies credit card applications as **"good"** or **"bad"** based on applicant information and credit history. It covers:

- **Data Preprocessing**: Handling missing values and feature engineering (e.g., Age, WorkingYears).
- **Imbalanced Data Handling**: Balancing classes using SMOTE.
- **Modeling**: Training a baseline Random Forest classifier.
- **Hyperparameter Optimization**: Tuning model parameters with Optuna.
- **Evaluation**: Measuring performance using Accuracy, Precision, Recall, and F1-score.

## 📂 Dataset

The dataset consists of two CSV files, which should be merged on the applicant ID:

1. **`application_record.csv`**
   - Demographic and socio-economic features (e.g., CODE_GENDER, AMT_INCOME_TOTAL, NAME_EDUCATION_TYPE).
2. **`credit_record.csv`**
   - Monthly repayment status (MONTHS_BALANCE) and payment status codes.

## ⚙️ Prerequisites

- Python 3.7+
- Jupyter Notebook or JupyterLab
- Required Python libraries:
  - pandas
  - numpy
  - scikit-learn
  - imbalanced-learn
  - matplotlib
  - seaborn
  - optuna

## 🚀 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/<username>/credit-approval-ml-project.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## ▶️ Usage

1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Open `credit-approval-ml-project.ipynb`.
3. Execute cells in order to follow data preprocessing, model training, and evaluation.

## 📝 Notebook Structure

1. **Data Preprocessing**
   - Load and merge CSV files
   - Analyze and clean missing values
   - Feature engineering (Age, WorkingYears)
2. **Imbalanced Data Handling**
   - Encode categorical variables
   - Apply SMOTE for oversampling
3. **Modeling**
   - Split data into training and testing sets
   - Train a baseline Random Forest model
   - Optimize hyperparameters with Optuna
4. **Evaluation**
   - Compare models and report performance metrics

## 📊 Results Summary

Below is the performance table for the Random Forest model optimized with Optuna:

|               | precision | recall | f1-score | support |
|---------------|-----------|--------|----------|---------|
| **0**         | 0.97      | 0.98   | 0.98     | 85286   |
| **1**         | 0.98      | 0.97   | 0.98     | 85110   |
| **accuracy**  |           |        | **0.98** | 170396  |
| **macro avg** | 0.98      | 0.98   | 0.98     | 170396  |
| **weighted avg** | 0.98   | 0.98   | 0.98     | 170396  |


## 🤝 Contributing

1. Fork this repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add some feature"
   ```
4. Push to your branch:
   ```bash
   git push origin feature/your-feature
   ```
5. Open a Pull Request.
