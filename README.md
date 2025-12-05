# DM4Edu : Predicting Academic Performance Based On Student Behavior

## Overview

This project is a data mining study which aims at predicting students' final exam scores **(exam_score)** based on an analysis of their behavioral, lifestyle and environmental factors.

### Objectives

The main objective is to predict the continuous variable exam_score

- Clean, transform and encode the data to prepare it for modeling.
- Validate the relationships between key habits and performance.
- Develop and evaluate regression models for student performance prediction.
- Create a simple risk flag for low-performing students

### Hypotheses


| Hypothesis | Summary | Finding |
| :--- | :--- | :--- |
| **H1 (Study Time)** | More hours studied $\rightarrow$ Higher exam scores. | **Supported:** Strong positive correlation ($\mathbf{+0.825}$). |
| **H2 (Screen Time)** | High screen time $\rightarrow$ Negative association with performance. | **Supported:** Negative correlation ($\mathbf{-0.238}$). |
| **H3 (Environmental Factors)** | Part-time job/Internet quality $\rightarrow$ Influence performance indirectly by affecting habits. | **Supported Indirectly:** Weak individual correlations observed. |

### Data & Preprocessing Summary

- **Dataset:** _**student_habits_performance.csv**_ (1000 rows, 16 columns).

- **Target:** _**exam_score**_ (Numeric, range 18.4–100).

- **Missing Values:** 91 missing values in _**parental_education_level**_ were imputed using the Mode (High School).

- **Categorical Feature Encoding:** Both ordinal and binary encoding is done on the categorical variables to prepare the data for model training.

- **Feature Engineering:** A composite feature, _**total_screen_time**_ _**(social_media_hours**_ **+** _**netflix_hours)**_, was created to capture overall digital distraction.

### Project Workflow - Pipeline (Excpected to be carried out)

| Phase | Detail | Metrics/Methods |
| :--- | :--- | :--- |
| **Data Splitting** | Split the cleaned dataset into training, testing, and cross-validation sets. | N/A |
| **Model Benchmarking** | Implement and test various regression models. | Linear Regression, Random Forest Regressor |
| **Model Evaluation** | Assess each model's predictive capability. | **MAE, RMSE, $\mathbf{R^{2}}$** (for regression) |
| **Interpretability** | Understand which factors drive the predictions. | Simple Feature Importance |
| **Risk Flag** | Evaluate potential classification metrics for the low-performance risk flag. | Precision, Recall, F1-score |


### Team Members
Ece Mina Örenler & İrem Batıgün

### Technologies

- Python
- **Data Manipulation:** Pandas
- **Modeling & Analysis:** Scikit-learn
- **Visualization:** Matplotlib, Seaborn
