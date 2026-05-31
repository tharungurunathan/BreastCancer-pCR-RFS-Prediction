# Breast Cancer pCR & RFS Prediction using Machine Learning

## Overview

This project presents a machine learning-based framework for predicting treatment response and survival outcomes in breast cancer patients. The objective is to assist in understanding patient prognosis by leveraging clinical and treatment-related data.

The project focuses on two important clinical endpoints:

* **Pathological Complete Response (pCR)** Prediction
* **Recurrence-Free Survival (RFS)** Prediction

By combining data preprocessing, feature engineering, feature selection, and machine learning algorithms, the project aims to generate reliable predictive models that can support oncology research and data-driven healthcare applications.

---

## Clinical Background

### Pathological Complete Response (pCR)

Pathological Complete Response refers to the absence of detectable invasive cancer cells after neoadjuvant treatment and surgery.

Achieving pCR is often associated with:

* Better treatment response
* Improved long-term outcomes
* Reduced recurrence risk

Accurate prediction of pCR before treatment can help clinicians evaluate therapy effectiveness and personalize treatment strategies.

---

### Recurrence-Free Survival (RFS)

Recurrence-Free Survival measures the duration during which a patient remains free from cancer recurrence after treatment.

Predicting RFS is important because it helps:

* Estimate patient prognosis
* Identify high-risk individuals
* Support follow-up planning
* Improve personalized healthcare decisions

---

## Project Objectives

The primary goals of this project are:

### 1. pCR Prediction

Develop a classification model capable of predicting whether a patient is likely to achieve pathological complete response following treatment.

### 2. RFS Prediction

Develop a predictive survival model capable of estimating recurrence-free survival outcomes using patient clinical characteristics.

---

## Dataset Description

The project utilizes structured tabular clinical data.

### Training Dataset

**File:** `TrainDataset2025.csv`

Used for:

* Data preprocessing
* Feature engineering
* Feature selection
* Model training
* Hyperparameter optimization
* Cross-validation

### Test Dataset

**File:** `FinalTestDataset2025.xls`

Used for:

* Model inference
* External evaluation
* Generating final predictions

---

## Machine Learning Workflow

The project follows a complete end-to-end machine learning pipeline.

### Step 1: Data Preprocessing

Raw clinical datasets often contain inconsistencies and missing information.

The preprocessing pipeline includes:

* Missing value handling
* Numerical feature cleaning
* Categorical feature processing
* Feature filtering
* Data transformation

This step ensures that the data is suitable for machine learning algorithms.

---

### Step 2: Feature Engineering

Feature engineering is performed to improve model performance by extracting meaningful information from available variables.

Techniques include:

* Feature selection
* Feature reduction
* Removal of redundant variables
* Identification of clinically relevant predictors

---

### Step 3: Model Development

Separate models are developed for each prediction task.

---

## pCR Prediction Pipeline

### Problem Type

Binary Classification

### Objective

Predict whether a patient achieves pathological complete response.

### Algorithm Used

**CatBoost Classifier**

CatBoost was selected because:

* Handles categorical features efficiently
* Reduces preprocessing requirements
* Performs well on structured medical datasets
* Provides robust performance on tabular data

### Workflow

1. Data preprocessing
2. Feature selection
3. Cross-validation
4. Model training
5. Performance evaluation
6. Model saving

### Generated Model

```text
catboost_fs_final.pkl
```

---

## RFS Prediction Pipeline

### Problem Type

Regression / Survival Outcome Prediction

### Objective

Estimate recurrence-free survival outcomes.

### Algorithms Used

* Missing Value Imputation
* Feature Selection
* Support Vector Regression (SVR)

### Why SVR?

Support Vector Regression is effective for:

* High-dimensional datasets
* Non-linear relationships
* Medical prediction tasks with limited sample sizes

### Workflow

1. Data preprocessing
2. Missing value imputation
3. Feature selection
4. Model training
5. Performance optimization
6. Prediction generation

### Generated Artifacts

```text
selected_features.pkl
num_imputer.joblib
svr_final_trained_on_all.joblib
```

---

## Repository Structure

```text
BreastCancer-pCR-RFS-Prediction
│
├── FinalTrainPCR.ipynb
├── FinalTestPCR.ipynb
├── FinalTrainRFS.ipynb
├── FinalTestRFS.ipynb
│
├── TrainDataset2025.csv
├── FinalTestDataset2025.xls
│
├── catboost_fs_final.pkl
├── selected_features.pkl
├── svr_final_trained_on_all.joblib
│
├── meta.json
├── to_drop.json
├── requirements.txt
└── README.md
```

---

## How to Run the Project

### Clone Repository

```bash
git clone https://github.com/tharungurunathan/BreastCancer-pCR-RFS-Prediction.git
cd BreastCancer-pCR-RFS-Prediction
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Running the pCR Model

### Training

Run:

```text
FinalTrainPCR.ipynb
```

Output:

```text
catboost_fs_final.pkl
```

### Prediction

Run:

```text
FinalTestPCR.ipynb
```

Input:

```text
FinalTestDataset2025.xls
```

Output:

Predicted pCR outcomes for unseen patients.

---

## Running the RFS Model

### Training

Run:

```text
FinalTrainRFS.ipynb
```

Outputs:

```text
selected_features.pkl
num_imputer.joblib
svr_final_trained_on_all.joblib
```

### Prediction

Run:

```text
FinalTestRFS.ipynb
```

Input:

```text
FinalTestDataset2025.xls
```

Output:

Predicted recurrence-free survival outcomes.

---

## Large File Notice

The file:

```text
num_imputer.joblib
```

is excluded from GitHub because it exceeds GitHub's 100 MB file size limit.

Download it here:

https://drive.google.com/file/d/19yjbSUrKR-S2_A78TTp-Yr4iyhkoH8JT/view?usp=sharing

Place the downloaded file in the project root directory before executing the RFS pipeline.

---

## Technologies & Libraries

* Python
* Pandas
* NumPy
* Scikit-Learn
* CatBoost
* LightGBM
* Optuna
* UMAP
* Category Encoders
* Joblib
* Jupyter Notebook

---

## Key Skills Demonstrated

This project showcases:

* Data Cleaning & Preprocessing
* Feature Engineering
* Feature Selection
* Classification Modeling
* Regression Modeling
* Hyperparameter Optimization
* Model Serialization
* Machine Learning Pipeline Development
* Healthcare Data Analytics

---

## Future Enhancements

Potential future improvements include:

* Deep Learning-based prediction models
* Explainable AI using SHAP
* Survival analysis techniques
* Interactive web deployment using Streamlit
* External clinical validation datasets
* Ensemble learning approaches

---

## Author

**Tharun Gurunathan**

Aspiring Data Scientist | Machine Learning Enthusiast | Healthcare Analytics Research

GitHub: https://github.com/tharungurunathan

---

## Disclaimer

This project is intended for educational, research, and portfolio purposes only. The predictions generated by these models are not intended for clinical diagnosis or treatment decisions without proper medical validation.
