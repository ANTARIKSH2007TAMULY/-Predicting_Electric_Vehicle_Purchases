# Predicting Electric Vehicle Purchases 🚗⚡

An end-to-end machine learning project for predicting whether a customer is likely to purchase an **Electric Vehicle (EV)**.

The project explores multiple machine learning and gradient-boosting approaches, including **LightGBM, XGBoost, CatBoost, and Logistic Regression**, followed by ensemble modeling and validation using **5-fold stratified Out-of-Fold (OOF) predictions**.

The competition metric is **ROC-AUC**, making the project focused on producing reliable probability estimates rather than simply predicting binary labels.

---

## 📌 Project Overview

The objective of this project is to predict the probability that a customer will purchase an Electric Vehicle based on customer demographics, financial information, commuting behavior, vehicle ownership, charging infrastructure, environmental concerns, and related features.

The target variable is:

```text
Will_Buy_EV
```

This project was developed for the **Kaggle Playground Series – Season 6 Episode 9: Predicting Electric Vehicle Purchases** competition.

---

## 🎯 Objective

The primary objective is to build a high-performing binary classification model that maximizes:

**ROC-AUC (Receiver Operating Characteristic – Area Under the Curve)**

The model generates probabilities between `0` and `1`, which are evaluated based on how effectively they rank EV buyers above non-buyers.

---

## 🧠 Machine Learning Workflow

```text
Raw Dataset
     ↓
Exploratory Data Analysis
     ↓
Data Preprocessing
     ↓
Feature Engineering
     ↓
5-Fold Stratified Cross-Validation
     ↓
Multiple ML Models
     ↓
OOF Predictions
     ↓
Model Comparison
     ↓
Ensemble / Blending
     ↓
Final Predictions
     ↓
Kaggle Submission
```

---

## 🤖 Models Used

### Logistic Regression

Used as the baseline classification model to establish a reference ROC-AUC against which more complex models could be evaluated.

### LightGBM

LightGBM was used for efficient gradient boosting on the structured/tabular dataset.

### XGBoost

XGBoost was evaluated for its ability to model nonlinear relationships and feature interactions using regularized gradient boosting.

### CatBoost

CatBoost was included as another powerful gradient-boosting approach, particularly useful for datasets containing categorical features.

---

## 🔄 Cross-Validation

The models were evaluated using **5-Fold Stratified Cross-Validation**.

For every fold:

1. Four folds were used for training.
2. One fold was used for validation.
3. Predictions were generated for the validation fold.
4. The process was repeated until every training observation had an OOF prediction.

This produces predictions for the complete training dataset where each prediction comes from a model that did not train on that particular observation.

---

## 📊 Model Performance

The earlier version of the notebook produced the following OOF ROC-AUC scores:

| Model             | 5-Fold OOF ROC-AUC |
| ----------------- | -----------------: |
| LightGBM          |       **0.941324** |
| XGBoost           |       **0.941542** |
| CatBoost          |       **0.941562** |
| Nelder-Mead Blend |       **0.941730** |

### Previous Kaggle Public Leaderboard

The earlier Kaggle submission achieved:

**Public LB ROC-AUC: 0.94138**

The current notebook's `submission.csv` has **not yet been submitted to Kaggle**, so no new public leaderboard score is reported.

---

## 🤝 Ensemble Modeling

The project also explores combining predictions from multiple gradient-boosting models.

The previous notebook used **Nelder-Mead optimization** to determine blending weights for the ensemble.

The previous ensemble achieved:

```text
Nelder-Mead Blend OOF ROC-AUC: 0.941730
```

This score is based on the 5-fold OOF validation protocol.

---

## 📈 Evaluation Metric

### ROC-AUC

ROC-AUC evaluates the ability of a binary classification model to distinguish positive and negative observations across different classification thresholds.

Since the Kaggle competition evaluates probabilities, the project focuses on generating probability predictions rather than only hard class predictions.

---

## 📦 Submission

The final predictions are stored in:

```text
submission.csv
```

The submission contains:

```text
Will_Buy_EV
```

The notebook also verifies:

* Number of rows
* Column names
* Missing values
* Minimum predicted probability
* Maximum predicted probability

---

## 🛠️ Technologies Used

### Programming

* Python

### Machine Learning

* Scikit-learn
* XGBoost
* CatBoost
* LightGBM

### Data Processing

* Pandas
* NumPy

### Visualization

* Matplotlib
* Seaborn

### Techniques

* Binary Classification
* Feature Engineering
* Stratified K-Fold Cross-Validation
* Out-of-Fold Predictions
* Gradient Boosting
* Ensemble Learning
* Model Blending
* Hyperparameter Optimization
* ROC-AUC Evaluation

---

## 🔬 Key Learning Outcomes

This project provided practical experience with:

* End-to-end tabular machine learning
* Binary classification
* Feature preprocessing
* Gradient-boosting algorithms
* Comparing different boosting frameworks
* Stratified cross-validation
* Out-of-Fold predictions
* ROC-AUC optimization
* Ensemble modeling
* Prediction blending
* Kaggle submission workflows
* Comparing local validation with leaderboard performance

---

## 🏆 Results Summary

```text
LightGBM          → 0.941324
XGBoost           → 0.941542
CatBoost          → 0.941562
Nelder-Mead Blend → 0.941730
```

### Kaggle Public Leaderboard

```text
Previous Submission → 0.94138
```

The **0.941730** value is a 5-fold OOF cross-validation result, while **0.94138** is the public Kaggle leaderboard score from the earlier submission. They represent different evaluation sources and should not be treated as identical metrics.

---

## 🚀 Future Improvements

* More extensive hyperparameter optimization
* Additional feature engineering
* Feature importance analysis
* SHAP-based model interpretation
* Probability calibration
* More diverse ensemble models
* Repeated cross-validation
* Further optimization of LightGBM, XGBoost, and CatBoost

---

## 👨‍💻 Author

### Antariksh Tamuly

Machine Learning | Data Science | AI | Python

**GitHub:**
https://github.com/ANTARIKSH2007TAMULY

**Kaggle:**
https://www.kaggle.com/tamulyantariksh

The project and Kaggle competition work can be explored through my Kaggle profile.

---

## 📜 Disclaimer

The reported **0.94138 Kaggle public leaderboard score** belongs to the earlier submission referenced in the notebook.

The current notebook generates a new `submission.csv`, but that submission has **not yet been evaluated on Kaggle's public leaderboard**. Therefore, the current notebook's OOF ROC-AUC should be considered a validation estimate rather than a new Kaggle leaderboard result.
