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

PCA was explored as a dimensionality-reduction technique to investigate whether the original feature space could be represented using a smaller number of components.

---

## Machine Learning Models


### Logistic Regression

Logistic Regression was used as a baseline statistical learning method because of its interpretability and suitability for binary classification.

### Support Vector Machine

Support Vector Machine (SVM) models were evaluated to capture potentially nonlinear relationships between predictors and the outcome.

### XGBoost

XGBoost was included as a gradient-boosting approach capable of modeling nonlinear relationships and interactions among predictors.

### Model Comparison

Different combinations of algorithms and feature sets were evaluated to compare predictive performance and identify a final model.

---

## Evaluation Metrics

### ROC-AUC

The **Area Under the Receiver Operating Characteristic Curve (AUC)** was used to evaluate the model's ability to distinguish between individuals with different levels of diabetes-related risk.

### Recall

Recall was emphasized because missing a high-risk individual may be more consequential than incorrectly identifying a lower-risk individual as high risk.

$$
Recall = \frac{TP}{TP + FN}
$$

where:

* **TP** = True Positives
* **FN** = False Negatives

A higher recall corresponds to fewer false negatives.

---

## Results

The final selected model was an **SVM using seven features selected through Random Forest-based feature selection**.

| Metric            |              Final SVM |
| ----------------- | ---------------------: |
| Selected Features |                      7 |
| AUC               |               **0.86** |
| Recall            |                **91%** |

The final model achieved an **AUC of 0.86**, indicating strong discriminatory performance.

The model also achieved **91% recall**, which aligned with the project's objective of minimizing false negatives in a risk-screening context.

Importantly, the final model used only **seven selected features**, providing a more compact representation of the predictor space while maintaining strong predictive performance.

---

## Limitations

Several limitations should be considered:

* NHANES is observational survey data, so the analysis does not establish causal relationships.
* Missing data and variable availability may affect model performance.
* Predictive performance may differ when the model is applied to populations outside the NHANES sample.
* Survey-weighted statistical analysis and machine learning models involve different assumptions and should be interpreted accordingly.
* The model is intended as a **risk prediction framework**, not as a clinical diagnostic tool.

---

## Tools & Technologies

* **Programming Language:** R
* **Dataset:** NHANES 2021–2023
* **Statistical / Machine Learning Methods:**

  * Logistic Regression
  * Support Vector Machine
  * XGBoost
  * Random Forest
  * Principal Component Analysis (PCA)
* **Evaluation Metrics:**

  * ROC-AUC
  * Recall
  * Classification performance metrics

---

## Project Structure

```text
NHANES-Diabetes-Risk-Prediction/
│
├── README.md
│
└── NHANES_Diabetes.R
```

The code reflects an **iterative analytical workflow** developed during the project. Some intermediate analyses and alternative modeling approaches were retained or commented out as different methods were evaluated.

Therefore, the repository is intended primarily to **document the analytical process, modeling decisions, and results**, rather than provide a fully automated end-to-end pipeline.

---

## Analysis Notes

The modeling workflow involved iterative experimentation with different preprocessing strategies, feature representations, and classification algorithms.

Some code sections were subsequently commented out or modified as the analysis evolved. As a result, the code may require adjustments to execution order or intermediate objects when rerun from scratch.

This repository should therefore be viewed as a record of the **data analysis and modeling process**, with the README summarizing the final methodology and results.

---
