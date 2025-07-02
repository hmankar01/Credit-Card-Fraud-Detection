# Credit Card Fraud Detection 💳

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

This repository showcases an end-to-end machine learning project for detecting fraudulent credit card transactions. The project implements a complete data science workflow, from exploratory data analysis and advanced feature engineering to model tuning and evaluation. The result is a high-precision **CatBoost** model optimized for real-world business applications.

## 🚀 Project Overview

The primary objective of this project was to develop a highly accurate and reliable model to identify fraudulent credit card transactions using a real-world dataset from **Capital One's Repository**. The final **CatBoost** model achieves **80% precision** on the validation set. This level of precision is crucial in a business context, as it minimizes false positives and enables a fraud investigation team to focus its efforts on high-confidence alerts.

***

## ✨ Key Features

* **Advanced Feature Engineering:** Developed sophisticated features including account tenure, time-based transaction patterns, and key financial ratios to capture complex fraudulent behaviors.
* **Robust Preprocessing Pipeline:** Implemented a custom `ColumnTransformer` pipeline that combines `TargetEncoding` for high-cardinality categorical features and `RobustScaler` to effectively handle outliers in numerical data.
* **Class Imbalance Handling:** Utilized the **SMOTE** (Synthetic Minority Over-sampling Technique) to address the severe class imbalance in the training data, ensuring the model learns to identify rare fraud cases.
* **Comparative Model Analysis:** Conducted in-depth training and hyperparameter tuning for Logistic Regression (Baseline), XGBoost, and CatBoost to identify the best-performing algorithm.
* **Optimized Decision Threshold:** Moved beyond the default 0.5 threshold by tuning the model's decision point to maximize the F1-score, striking an optimal balance between precision and recall for the business problem.

***

## 🛠️ Technology Stack

* **Core Libraries:** Python 3.x, Pandas, NumPy
* **Machine Learning:** Scikit-learn, XGBoost, CatBoost
* **Data Visualization:** Matplotlib, Seaborn
* **Development Environment:** Jupyter Notebook

***

## ⚙️ The Machine Learning Pipeline

### 1. Exploratory Data Analysis (EDA)
A thorough EDA revealed crucial insights, including a severe class imbalance and a heavily skewed distribution of transaction amounts. Log transformation was applied to normalize the transaction data, which significantly improved modeling performance.

![EDA Charts](EDA.png)
![Log Distribution of Transaction Amounts](Log_distribution.png)

### 2. Feature Engineering & Preprocessing
This stage focused on creating high-impact features and preparing the data for modeling. Key steps included:
* Creating flags for suspicious activities like rapid multi-swipes.
* Engineering time-based features such as account age and days until card expiration.
* Applying **SMOTE** to the training data to generate synthetic samples of the minority (fraud) class.

### 3. Model Training and Tuning
Three powerful classification models were trained and systematically evaluated:
1.  **Logistic Regression** (as a baseline)
2.  **XGBoost**
3.  **CatBoost**

Each model's hyperparameters were fine-tuned using `RandomizedSearchCV` with cross-validation to optimize performance.

***

## 📈 Results and Business Impact

The final analysis revealed a clear trade-off between precision and recall. While some models could identify a higher number of fraud cases (high recall), they generated too many false alarms, which is inefficient for a business.

![Hypothesis Visualization](Hypothesis.png)

The champion model, **CatBoost**, was selected for its exceptional **precision of 80%** after threshold tuning. This means that **4 out of 5 transactions flagged by the model are genuinely fraudulent**. Such high precision provides a reliable, high-confidence alert system that allows a fraud investigation team to work efficiently and minimize losses.

The confusion matrix below visualizes the final model's strong performance on the test set.

![Final Model Confusion Matrix](Confusion_Matrix.png)

***

## 🚀 Getting Started

Follow these steps to set up and run the project on your local machine.

### Prerequisites
* [Git](https://git-scm.com/)
* [Python 3.8+](https://www.python.org/downloads/)

### 1. Clone the Repository
Open your terminal and run the following commands to download the project and navigate into its directory.
```bash
# Clone the repository
git clone https://github.com/hmankar01/Credit-Card-Fraud-Detection.git
```
### Navigate into the project directory
```bash
cd Credit-Card-Fraud-Detection
```
### 2. Create and Activate a Virtual Environment ⚙️
This creates an isolated environment for the project's dependencies.

**On macOS/Linux:**
```bash
# Create a virtual environment
python3 -m venv venv

# Activate the virtual environment
source venv/bin/activate
```
**On Windows:**
```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
venv\Scripts\activate
```
### 3. Install Required Libraries 📦
This command installs all the necessary Python packages listed in the requirements.txt file.
```Bash
pip install -r requirements.txt
```
### 4. Launch the Jupyter Notebook 🚀
Now you can start the Jupyter environment to view and run the analysis notebook.
```bash
jupyter notebook
```
A new tab will open in your browser. From there, click on the Credit_Fraud_analysis_.ipynb file to get started.

### 📫 Contact Me
Harsh Mankar- harshrajendramankar@gmail.com | https://www.linkedin.com/in/hmankar01/

Project Link: https://github.com/hmankar01/Credit-Card-Fraud-Detection.git

