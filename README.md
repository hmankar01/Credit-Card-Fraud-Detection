# Credit Card Fraud Detection 💳

This repository contains an end-to-end machine learning project for detecting fraudulent credit card transactions. The pipeline covers everything from data cleaning and feature engineering to model training, evaluation, and tuning, culminating in a high-precision classification model ready for a business context.

***

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Key Features](#-key-features)
- [Technologies Used](#-technologies-used)
- [The Machine Learning Pipeline](#-the-machine-learning-pipeline)
- [Results & Conclusion](#-results--conclusion)
- [How to Run This Project](#-how-to-run-this-project)

***

## 🚀 Project Overview

The goal of this project is to develop a highly accurate and reliable model to identify fraudulent credit card transactions. Using a real-world dataset, the project demonstrates a complete machine learning workflow. The final model, **CatBoost**, achieves **80% precision** on the validation set, making it highly effective for minimizing false alarms and allowing a fraud investigation team to focus on high-confidence alerts.

## ✨ Key Features

* **Advanced Feature Engineering:** Creation of sophisticated features like account age, time-based patterns, and financial ratios.
* **Robust Preprocessing:** A custom pipeline that includes `Target Encoding` for categorical features, `RobustScaler` to handle outliers, and `SMOTE` to correct for severe class imbalance.
* **Comparative Model Analysis:** In-depth training and tuning of Logistic Regression, XGBoost, and CatBoost models.
* **Threshold Tuning:** A custom evaluation class was used to find the optimal decision threshold based on the F1-score, moving beyond default settings to maximize model performance in a real-world scenario.

## 🛠️ Technologies Used

* **Python 3.x**
* **Pandas & NumPy:** For data manipulation and numerical operations.
* **Scikit-learn:** For preprocessing, modeling, and evaluation.
* **XGBoost & CatBoost:** For advanced gradient boosting models.
* **Matplotlib & Seaborn:** For data visualization.
* **Jupyter Notebook:** For analysis and code development.

***

## ⚙️ The Machine Learning Pipeline

### 1. Exploratory Data Analysis (EDA)

A deep dive into the dataset revealed key transaction patterns, time-based trends, and a severe class imbalance. The distribution of transaction amounts was heavily skewed, requiring a log transformation to normalize it for better modeling performance.

![EDA Charts](EDA.png)
![Log Distribution of Transaction Amounts](Log_distribution.png)

### 2. Feature Engineering & Preprocessing

Created new, impactful features and built a robust preprocessing pipeline to prepare the data for modeling. This included:
* Flags for suspicious activities like multi-swipes.
* Time-based features such as account age and days to card expiration.
* A `ColumnTransformer` pipeline with `RobustScaler` for numerical features and `TargetEncoder` for high-cardinality categorical features.
* Application of **SMOTE** to the training data to handle the severe class imbalance.

### 3. Model Training and Tuning

Three models were trained and evaluated:
1.  **Logistic Regression** (Baseline)
2.  **XGBoost**
3.  **CatBoost**

Each model was tuned using `RandomizedSearchCV` to find the optimal hyperparameters.

***

## 📈 Results & Conclusion

The final analysis highlighted a trade-off between precision and recall. While some models could catch more fraud (high recall), they did so at the cost of many false alarms.

![Hypothesis Visualization](Hypothesis.png)

The champion model, **CatBoost**, was selected for its outstanding **precision of 80%** after threshold tuning. This means that 4 out of 5 transactions flagged by the model are indeed fraudulent, providing a high-confidence alert system for business use. The confusion matrix below illustrates its strong performance.

![Final Model Confusion Matrix](Confusion_Matrix.png)

This high-precision model is ideal for real-world deployment, as it ensures that the fraud investigation team's time is spent on legitimate alerts.

***

## 🚀 How to Run This Project

### 1. Clone the Repository
```bash
git clone [https://github.com/hmankar01/Credit-Card-Fraud-Detection.git](https://github.com/hmankar01/Credit-Card-Fraud-Detection.git)
cd Credit-Card-Fraud-Detection
