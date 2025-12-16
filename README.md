# DM4Edu: Predicting Academic Performance Based on Student Behavior

## Overview

This project applies data mining techniques to predict students’ final exam scores (*exam_score*) based on behavioral, lifestyle, and environmental factors.  
Beyond score prediction, a **regression-based risk flag** is implemented to identify students who may be at risk of low academic performance, supporting early warning and intervention strategies.

The project follows the **KDD (Knowledge Discovery in Databases)** process from data selection to evaluation and interpretation.

---

## Objectives

The main objective is to predict the continuous variable *exam_score* using machine learning models.

- Clean, preprocess, and encode the dataset for modeling  
- Explore relationships between student habits and academic performance  
- Train and compare multiple regression models  
- Apply cross-validation and hyperparameter tuning  
- Select the best-performing model based on evaluation metrics  
- Generate a risk flag for low-performing students (*exam_score < 60*)  

---

## Hypotheses

| Hypothesis | Summary | Finding |
| :--- | :--- | :--- |
| **H1 (Study Time)** | More study hours → Higher exam scores | **Supported:** Strong positive correlation |
| **H2 (Screen Time)** | Higher screen time → Lower performance | **Supported:** Negative correlation observed |
| **H3 (Environmental Factors)** | Environmental factors indirectly influence performance | **Supported Indirectly:** Weak individual effects |

---

## Data & Preprocessing Summary

- **Dataset:** `student_habits_performance.csv`  
- **Rows:** 1000  
- **Original Features:** 16  
- **Target Variable:** *exam_score* (numeric, range 18.4–100)

### Missing Value Handling

- Missing values in *parental_education_level* were imputed using the mode.

### Encoding

- Binary encoding (Yes/No variables)  
- Ordinal encoding (*diet_quality*)  
- One-hot encoding (*gender, internet_quality, parental_education_level*)

---

## Feature Engineering

- **total_screen_time** = social_media_hours + netflix_hours  
- **environmental_score**: a composite feature derived from environmental variables using correlation-based weighting  

After encoding and feature engineering, the final dataset contains **fully numeric features** suitable for modeling.

---

## Modeling & Evaluation

| Phase | Description | Methods / Metrics |
| :--- | :--- | :--- |
| Data Splitting | Train/test split | 80% train / 20% test |
| Baseline | Mean predictor | MAE |
| Regression Models | Multiple models trained and compared | Linear Regression, Random Forest, XGBoost, CatBoost |
| Hyperparameter Tuning | Model optimization | GridSearchCV |
| Cross-Validation | Model robustness | 5-fold CV (MAE) |
| Evaluation | Regression performance | MAE, RMSE, R² |
| Interpretability | Model explanation | Feature Importance |
| Risk Flag | Early warning classification | Accuracy, Precision, Recall, F1-score, Confusion Matrix |

---

## Risk Flag (Early Warning System)

Although the primary task is regression, a **binary risk flag** is derived by thresholding the predicted exam score:

- **At risk:** predicted_exam_score < 60  
- **Not at risk:** predicted_exam_score ≥ 60  

This enables the model to function as an **early warning system**, identifying students likely to underperform.

---

## Technologies

- **Programming Language:** Python  
- **Data Manipulation:** Pandas, NumPy  
- **Modeling & Evaluation:** Scikit-learn, XGBoost, CatBoost  
- **Visualization:** Matplotlib, Seaborn  

---

## Team Members

- Ece Mina Örenler  
- İrem Batıgün  
