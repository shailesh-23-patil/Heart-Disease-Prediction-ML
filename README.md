# Heart Disease Prediction ML

Repository: Heart-Disease-Prediction-ML

This project focuses on predicting whether a patient is likely to have heart disease based on clinical and lifestyle-related features. It combines data cleaning, exploratory analysis, feature engineering, and predictive modeling.

## Project Goal

The main objective is to build a model that can classify whether a patient has heart disease using parameters such as age, cholesterol, resting blood pressure, chest pain type, exercise-induced angina, max heart rate, and other medical indicators.

## Dataset

- File: `heart.csv`
- Target variable: `HeartDisease`
- Features include:
  - `Age`
  - `Sex`
  - `ChestPainType`
  - `RestingBP`
  - `Cholesterol`
  - `FastingBS`
  - `RestingECG`
  - `MaxHR`
  - `ExerciseAngina`
  - `Oldpeak`
  - `ST_Slope`

## Data Cleaning and Data Quality Issues

A major part of this project is identifying hidden data-quality problems:

- Cholesterol values of `0` are impossible for a living person and were treated as missing values.
- Resting blood pressure values of `0` were also treated as missing.
- A missing-value flag was added so the model could learn whether the absence of a measurement itself was informative.
- The data was cleaned before modeling to avoid leakage and misleading results.

## Exploratory Data Analysis

The notebook explores patterns such as:

- heart disease rate by age and cholesterol
- relationship between chest pain type and disease occurrence
- differences in heart disease prevalence by sex
- variation in max heart rate and blood pressure
- features like `ST_Slope`, `ExerciseAngina`, and `FastingBS` as strong clinical indicators

## Feature Engineering

The analysis creates several engineered features, including:

- `Cholesterol_missing` flag
- `HighBP`
- `HighCholesterol`
- `AgeGroup`
- `RiskScore`

This improves the ability of the model to capture combinations of medical factors that are clinically meaningful.

## Modeling Approach

The workflow uses a proper supervised learning pipeline:

- stratified train/test split to preserve disease ratio
- preprocessing inside a `ColumnTransformer`
- imputation for missing values using median
- scaling for numerical features
- one-hot encoding for categorical features
- models compared:
  - Logistic Regression
  - Random Forest Classifier
- performance measured by:
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - ROC-AUC
  - confusion matrix

## Key Insights

- Missing cholesterol values were not random; they were informative.
- Recall is especially important in a heart-disease model, because failing to detect a sick patient can be far more serious than a false positive.
- The model achieved strong classification performance using clinical features.
- Logistic Regression was a strong and interpretable option, while Random Forest also performed competitively.
- Top predictors are often related to risk factors such as age, blood pressure, cholesterol, and exercise-related symptoms.

## Tech Stack

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- scikit-learn
- Jupyter Notebook

## Files in This Project

- `heart_fixed.ipynb` — complete analysis and modeling notebook
- `heart.csv` — dataset for training and evaluation

## How to Run

```bash
jupyter notebook heart_fixed.ipynb
```

## Important Note

This is a learning and demonstration project for machine learning and healthcare analytics. It should not be treated as a real medical diagnosis tool.

## Project Summary

This project demonstrates how to handle real-world healthcare data responsibly, use feature engineering to improve model quality, and compare interpretable and tree-based classifiers for binary medical prediction.
