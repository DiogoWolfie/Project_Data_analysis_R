# Predicting Income Levels: A Machine Learning Analysis of the UCI Adult Census Dataset

## Project Overview
This project analyzes the **UCI Adult Census Income dataset** to identify the demographic and socioeconomic factors that influence whether an individual earns **over \$50K per year**.  
The analysis includes a full **data cleaning, feature engineering, visualization**, and **machine learning modeling** pipeline, with both **Logistic Regression** and **Random Forest** approaches.

---

## Objectives
- Clean and preprocess the raw data from the UCI Adult dataset.
- Engineer meaningful features to improve model interpretability and accuracy.
- Visualize income-related patterns using **ggplot2**.
- Build predictive models to classify income levels.
- Evaluate model performance with metrics such as **Accuracy**, **Precision**, **Recall**, **F1**, and **AUC**.

---

## Dataset
- **Source:** [UCI Machine Learning Repository – Adult Dataset](https://www.kaggle.com/datasets/uciml/adult-census-income)
- **Records:** 32,561 individuals
- **Features:** 14 attributes (demographic, occupational, and financial)
- **Target Variable:** `income` (`<=50K` or `>50K`)

---

## Project Workflow

### **Step 1: Data Cleaning and Preparation**
- Handled missing values represented by `"?"`.
- Imputed missing `workclass` and `occupation` using logical and probabilistic methods.
- Checked redundancy between `education` and `education-num`.
- Removed whitespace in categorical variables.

### **Step 2: Feature Engineering**
- Grouped all non–U.S. entries in `native-country` as `"Other"`.
- Created binary target variable: `income` → 0 (`<=50K`) / 1 (`>50K`).
- Discretized `age` into groups: *Young*, *Adult*, *Senior*.
- Created new variable `net_capital = capital.gain - capital.loss`.

### **Step 3: Exploratory Data Analysis (EDA)**
- Visualized:
  - Income vs Education Level
  - Work Hours vs Income
  - Marital Status Impact
  - Age Distribution by Income Class
  - Custom insights by Gender, Race, and Age Groups

### **Step 4: Modeling and Evaluation**
- One-hot encoded categorical variables using **fastDummies**.
- Trained:
  - **Logistic Regression** (baseline model)
  - **Random Forest** (ensemble model)
- Evaluated models using:
  - Confusion Matrix
  - Accuracy, Precision, Recall, F1
  - ROC Curve and AUC
  - Feature Importance (Top 5 variables)

---

## Results Summary

| Metric | Logistic Regression | Random Forest |
|:-------|:--------------------:|:--------------:|
| Accuracy | ~83% | ~86% |
| Precision | ↑ | ↑ |
| Recall | Moderate | High |
| AUC | 0.90 | 0.91 |

**Random Forest** outperformed Logistic Regression across most metrics, while maintaining interpretability through feature importance analysis.

---

## Top 5 Most Important Features (Random Forest)
1. **education-num**  
2. **marital-status_Married-civ-spouse**  
3. **age**  
4. **hours-per-week**  
5. **occupation_Exec-managerial**

---

## Technologies Used
- **Language:** R
- **Libraries:**  
  `tidyverse`, `caret`, `ggplot2`, `fastDummies`, `randomForest`, `pROC`, `rcompanion`
- **Tools:** RStudio, R Markdown, GitHub

---

## Authors
**Team IDK**  
- Diogo Pereira Lobo  
- Eunsang Lee

*Project completed as part of the Data Science module — 2025.*


