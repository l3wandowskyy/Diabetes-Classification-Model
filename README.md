# Diabetes Classification Model

A machine learning project focused on predicting diabetes based on medical diagnostic measurements using several classification algorithms.

## Overview

This project aims to develop a binary classification model capable of predicting whether a patient has diabetes based on diagnostic medical attributes. The primary goal is to create a reliable decision-support tool that assists in early diagnosis, potentially improving patient care and outcomes.

## Project Objective

The objective of this project is to use machine learning techniques to analyze patient health data and predict diabetes occurrence. Early detection of diabetes is critical for effective treatment and prevention of severe complications such as heart disease, kidney failure, and nerve damage.

## Dataset Description

The dataset used in this project comes from the Pima Indians Diabetes Database, provided by the National Institute of Diabetes and Digestive and Kidney Diseases.
It contains 768 samples and 9 attributes collected exclusively from female patients aged 21 or older of Pima Indian heritage.

| **Feature** | **Description** |
|----------------|-------------------|
| **Pregnancies** | Number of pregnancies |
| **Glucose** | Plasma glucose concentration |
| **BloodPressure** | Diastolic blood pressure (mm Hg) |
| **SkinThickness** | Triceps skinfold thickness (mm) |
| **Insulin** | Serum insulin (μU/ml) |
| **BMI** | Body Mass Index (weight in kg / height in m²) |
| **DiabetesPedigreeFunction** | A function that scores likelihood of diabetes based on family history |
| **Age** | Age in years |
| **Outcome** | Target variable (1 = diabetic, 0 = non-diabetic) |

## Data Preprocessing

The dataset was thoroughly analyzed and cleaned before training the models:
- **Removed duplicates** to ensure data integrity.
- **Checked for missing values** - none were found.
- **Converted non-numeric columns** (`BMI`, `DiabetesPedigreeFunction`) to numeric.
- **Replaced zero values** in columns such as `Glucose`, `BloodPressure`, and `BMI` with their respective mean values.
- **Handled outliers** using the IQR method.
- **Standardized features** to ensure uniform scaling across attributes.
- **Split dataset** into training and test sets (80%/20%).

## Model Development

Four models were trained and evaluated:
1. **K-Nearest Neighbors (KNN)** - benchmark model.
2. **Decision Tree Classifier**.
3. **Random Forest Classifier**.
4. **Logistic Regression**.

**Model Selection**
- **KNN** - simple, interpretable baseline relying on similarity between patients.
- **Decision Tree** - handles nonlinear relationships effectively.
- **Random Forest** - robust against overfitting, handles complex data structures.
- **Logistic Regression** - well-established, interpretable model for binary classification.

## Model Evaluation & Results

Each model was trained using cross-validation, and performance was measured with accuracy, precision, recall, and F1-score.

| Model | Accuracy | Precision | Recall | F1-Score |
|--------|-----------|------------|---------|-----------|
| KNN | 77.4% | 69% | 44% | 54% |
| Decision Tree | 79.3% | 65.6% | 60.6% | 62.9% |
| Random Forest | 77.1% | 69.4% | 65.2% | 67.2% |
| Logistic Regression | 77.6% | 68.5% | 56.1% | 61.7% |

## Model Comparison & Hyperparameter Tuning

| **Model** | **Tuning Method** | **Key Hyperparameters** |
|------------|-------------------|--------------------------|
| **K-Nearest Neighbors (KNN)** | Grid Search | *k = 21* |
| **Decision Tree** | Grid Search | *criterion = 'entropy'*<br>*max_depth = 7*<br>*min_samples_leaf = 2*<br>*min_samples_split = 12* |
| **Random Forest** | Random Search | *n_estimators = 100*<br>*min_samples_split = 10*<br>*bootstrap = False* |
| **Logistic Regression** | Grid Search | *C = 0.1*<br>*penalty = 'L2'*<br>*solver = 'liblinear'* |

### **Best Model**

The **Random Forest Classifier** achieved the highest **F1-score (0.67)** and demonstrated the most balanced trade-off between **precision** and **recall**.  
It was therefore selected as the **final model** for this project.

## Potential Applications
- **Early diagnosis** of diabetes risk.
- **Health monitoring** and preventive care systems.
- **Research support** in medical data analysis.

## Authors 

- Jakub Lewandowski
- Witold Pietruszkiewicz
