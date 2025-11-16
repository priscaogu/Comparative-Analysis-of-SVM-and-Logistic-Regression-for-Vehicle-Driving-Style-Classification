

# Traffic Congestion Prediction Using On-Board Vehicle Sensor Data

This repository contains the full workflow, code, analysis, and modelling pipeline for predicting **traffic congestion levels** using multi-vehicle sensor datasets. The project compares **Logistic Regression** and **Support Vector Machines (SVM)**, incorporating SMOTE balancing, feature engineering, cost-function evaluation, and model performance assessment.


## **Project Overview**

Modern vehicles generate rich sensor data that can be used to identify and predict traffic congestion patterns. This project applies machine-learning techniques to four real-world OBD datasets (Peugeot207_01, Peugeot207_02, OpelCorsa_01, OpelCorsa_02) to classify congestion into:

* **Low**
* **Normal**
* **High**

Two supervised learning algorithms are benchmarked:

* **Logistic Regression (multi-class softmax)**
* **Support Vector Machine (SVM) with hinge loss**



## **Key Components**

### **1. Exploratory Data Analysis (EDA)**

* Missing value inspection (less than 0.2% across features).
* Correlation analysis to identify multicollinearity.
* Visualisations (heatmaps, distribution plots, congestion frequency).

### **2. Feature Engineering and Selection**

* Scaling using **StandardScaler**.
* Cyclical and one-hot encoding for temporal and categorical features.
* ANOVA **F-tests** for numerical feature ranking.
* Removal of redundant or low-variance predictors.

### **3. Handling Class Imbalance**

* Application of **SMOTE (Synthetic Minority Oversampling Technique)**.
* Visual before/after comparisons of class distribution.

Example visual:
Class imbalance bar charts
SMOTE-balanced bar charts


## **Model Building**

Two models were trained and evaluated on the balanced datasets:

### **Logistic Regression**

* Optimises the **Log-Loss (Cross-Entropy)** cost function.
* Performs well on probability-based prediction and calibrated outputs.

### **Support Vector Machine (SVM)**

* Optimises the **Hinge Loss** cost function.
* Excels at separating minority congestion classes.


## **Cost Function Evaluation**

Cost functions were computed on both **training and testing sets** for each dataset:

* **Low values** → better model fit
* **Small train–test difference** → good generalisation

Summary:

* Logistic Regression showed consistently lower **Log-Loss**.
* SVM had higher **Hinge Loss**, but excellent generalisation (small disparities).
* No signs of overfitting across any dataset.


## **Model Evaluation**

Metrics used:

* **Confusion Matrix**
* **Precision, Recall, F1-Score**
* **Macro- and Weighted Averages**
* **ROC Curves (per dataset)**
* **Feature importance/selection summary**

Key findings:

* SVM outperformed Logistic Regression for minority congestion classes.
* Best LR performance occurred in **OpelCorsa_02** (lowest Log-Loss: 0.298).
* Most challenging dataset: **Peugeot207_01** (highest LR Log-Loss: 0.647).


# **References**

* Chawla, N.V. et al. (2002). *SMOTE: Synthetic Minority Oversampling Technique.*
* scikit-learn documentation. Available at: [https://scikit-learn.org/stable/model_selection.html](https://scikit-learn.org/stable/model_selection.html)
* Nama, A. (2024). *Understanding Cost Functions in Machine Learning*. Available at: [https://medium.com/@anishnama20/understanding-cost-functions-in-machine-learning-types-and-applications-cd7d8cc4b47d](https://medium.com/@anishnama20/understanding-cost-functions-in-machine-learning-types-and-applications-cd7d8cc4b47d)


# **Author**

**Chidimma Ogu**
Machine Learning & Data Science Researcher


