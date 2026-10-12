# Heart Disease Prediction ML

A machine learning project that analyzes clinical data and builds classification models to predict the likelihood of heart disease based on patient health indicators.

## Project Goal

The objective is to explore relationships between clinical features and heart disease, perform data cleaning and feature engineering, and compare machine learning models for binary classification.

The project demonstrates a complete machine learning workflow, including exploratory data analysis, preprocessing, model training, and performance evaluation.

## Dataset

- **Dataset:** `heart.csv`
- **Target variable:** `HeartDisease`
- **Features:**
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

## Data Cleaning and Quality Checks

The project investigates data-quality issues and prepares the dataset for machine learning:

- Identifies potentially invalid zero values in cholesterol and resting blood pressure.
- Handles missing or invalid measurements using appropriate preprocessing techniques.
- Creates missing-value indicators where appropriate.
- Checks data consistency before model training.
- Separates training and testing data to help prevent data leakage.

**Note:** Zero cholesterol and blood pressure values should be reviewed in the context of the dataset before being treated as missing.

## Exploratory Data Analysis (EDA)

The notebook explores patterns and relationships involving:

- Heart disease prevalence across age groups.
- Relationships between chest pain type and heart disease.
- Differences in disease prevalence by sex.
- Cholesterol and resting blood pressure distributions.
- Maximum heart rate and exercise-induced angina.
- Clinical indicators such as `ST_Slope`, `FastingBS`, and `Oldpeak`.

Visualizations help identify trends, distributions, and potential relationships in the data.

## Feature Engineering

The project investigates additional features that may help capture useful patterns:

- `Cholesterol_missing` — indicates missing or invalid cholesterol measurements.
- `HighBP` — represents elevated blood pressure based on a defined threshold.
- `HighCholesterol` — represents elevated cholesterol based on a defined threshold.
- `AgeGroup` — groups patients into age categories.
- `RiskScore` — combines selected indicators according to the project's defined logic.

The usefulness of engineered features should be evaluated using appropriate validation methods.

## Machine Learning Approach

The project follows a supervised learning workflow.

### Data Preprocessing

- Stratified train/test split to preserve class proportions.
- Numerical feature imputation where required.
- Feature scaling for models that benefit from standardized numerical inputs.
- One-hot encoding for categorical variables.
- Preprocessing pipelines using Scikit-learn.

### Models

- Logistic Regression
- Random Forest Classifier

### Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix

These metrics provide different perspectives on model performance. Recall and false-negative rates are particularly important to examine in healthcare classification.

## Key Areas of Analysis

The project investigates:

- The relationship between clinical indicators and heart disease.
- The impact of data cleaning and feature engineering.
- Differences between Logistic Regression and Random Forest.
- The trade-off between detecting positive cases and generating false positives.
- Model performance on unseen test data.

Actual findings and model scores are available in the Jupyter Notebook.

## Technology Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Structure

```text
Heart-Disease-Prediction-ML/
├── heart.csv
├── heart_fixed.ipynb
└── README.md
```

## How to Run

### 1. Install the required libraries

Make sure Python and Jupyter Notebook are installed, then run:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 2. Open the project directory

Navigate to the folder containing the dataset and notebook.

### 3. Launch Jupyter Notebook

```bash
jupyter notebook heart_fixed.ipynb
```

### 4. Run the notebook

Execute the cells sequentially to reproduce the analysis and model evaluation.

## Project Objectives

- Clean and explore healthcare-related data.
- Investigate features associated with heart disease.
- Apply feature engineering and preprocessing.
- Train and compare classification models.
- Evaluate models using multiple classification metrics.
- Demonstrate practical machine learning skills.

## Conclusion

Heart Disease Prediction ML is an educational machine learning project demonstrating data preprocessing, exploratory analysis, feature engineering, classification, and model evaluation using clinical data.

## Disclaimer

This project is intended for educational and research purposes only. It is not a medical diagnostic tool and must not be used to make clinical decisions. Predictions require appropriate clinical validation before any real-world healthcare use.

---

**Author:** Shailesh Patil

**Project Type:** Machine Learning — Binary Classification