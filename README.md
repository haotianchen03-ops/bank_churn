# Bank Customer Churn Prediction & Behavioral Segmentation

## Objective

This project focuses on developing a predictive model for customer churn and analyzing customer behavioral segments to identify key factors of churn and propose actionable retention strategies.

- Develop a machine learning model to predict customer churn.
- Analyze the behavioral profile of churned customers.
- Identify key factors associated with customer departure.
- Provide a possible strategy.

---

## Dataset

The dataset includes:

- **Customer basic information** (age, gender, geography, etc.)
- **Behavioral data** (number of products, account activity, complaints, etc.)
- **Financial indicators** (account balance, estimated salary, etc.)
- **Target variable:** `Exited` (1 = churned, 0 = retained)

### Data Leakage Handling

The feature `Complain` showed a very strong correlation with `Exited`, indicating potential data leakage.  
To ensure realistic model performance, this variable was removed before training.

---

## Model Development

### 1️⃣ Model Comparison

The following models were evaluated using cross-validation:

- Logistic Regression  
- Random Forest  
- XGBoost  
- LightGBM  

Evaluation metric: **ROC-AUC**

LightGBM was selected as the optimal model with an AUC of approximately **0.82** during initial evaluation.

---

### 2️⃣ Hyperparameter Optimization

Hyperparameters were optimized using:

- `RandomizedSearchCV`
- `StratifiedKFold` cross-validation

After tuning, the AUC improved to approximately **0.86**.

---

## Model Explainability

SHAP was used to:

- Identify the most influential churn drivers
- Interpret model behavior
- Provide business-level insights

Key churn drivers identified:

- Number of Products
- IsActiveMember
- Age (around 38 particularly sensitive)
- Account Balance

---

### Clustering Approach

- Optimal number of clusters determined via **Elbow Method** (k = 3)
- 2D visualization performed using **PCA**


## Strategy

Based on modeling and segmentation results:

- Propose bundled offers (e.g., savings + insurance)
- Target less active members
- Focus on customers with fewer products
- Develop engagement strategies for high-risk age groups

---
