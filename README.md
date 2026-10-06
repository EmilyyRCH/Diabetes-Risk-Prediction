# Diabetes-Risk-Prediction
# Diabetes Risk Prediction Using NHANES 2021–2023

## Overview

This project investigates the use of statistical and machine learning methods to predict diabetes and pre-diabetes risk using data from the **National Health and Nutrition Examination Survey (NHANES) 2021–2023**.

The analysis compares multiple classification approaches, including **Logistic Regression, Support Vector Machine (SVM), and XGBoost**, and explores feature selection and dimensionality reduction using **Random Forest feature importance and Principal Component Analysis (PCA)**.

Because the project is designed as a risk-screening application, particular attention was given to **recall and false-negative reduction**.

**Final Model:** Support Vector Machine (SVM)
**Selected Features:** 7
**AUC:** 0.86
**Recall:** 91%

---

## Objectives

The main objectives of this project were to:

* Identify important predictors associated with diabetes and pre-diabetes risk.
* Develop models for individual-level risk prediction.
* Compare different classification algorithms and feature sets.
* Explore feature selection and dimensionality reduction techniques.
* Prioritize recall to reduce false negatives.

---

## Dataset

The analysis uses approximately **5,000 observations from NHANES 2021–2023**.

NHANES is a nationally representative survey conducted by the **National Center for Health Statistics (NCHS)**. It combines questionnaire, physical examination, and laboratory data to study the health and nutritional status of the U.S. population.

The dataset contains information across several domains, including:

* Demographic characteristics
* Anthropometric measurements
* Health conditions
* Laboratory measurements
* Lifestyle and behavioral factors
* Diabetes-related variables

### Survey Design

Because NHANES uses a complex probability sampling design, **NHANES survey weights** were considered in the analysis to account for unequal probabilities of selection and support more appropriate population-level interpretation.

---

## Methodology

### 1. Data Preparation

The raw NHANES data were processed and prepared for statistical modeling.

Key steps included:

* Data cleaning and variable selection
* Handling missing observations
* Preparing the target variable
* Encoding categorical variables
* Preparing predictors for machine learning models
* Incorporating NHANES survey weights where appropriate

---

### 2. Exploratory Data Analysis

Exploratory analysis was conducted to examine:

* Predictor distributions
* Relationships between predictors and diabetes-related outcomes
* Differences between outcome groups
* Potentially important demographic and health characteristics
* Missing-data patterns

This stage was used to guide subsequent feature selection and modeling decisions.

---

### 3. Feature Selection and Dimensionality Reduction

Two approaches were explored to identify useful representations of the predictor space.

#### Random Forest Feature Importance

Random Forest was used to evaluate feature importance and identify a smaller subset of predictors with strong predictive value.

The selected features were subsequently used in downstream models.

#### Principal Component Analysis (PCA)

PCA was explored as a dimensionality-reduction
