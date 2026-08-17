# Week 4 – Heart Disease Prediction

## 📌 Overview

This project is part of the **SkillNexis AI/ML Internship – Week 4**.

The objective is to build a Machine Learning classification model that predicts whether a patient has heart disease based on clinical and demographic features.

The project demonstrates data preprocessing, model training, evaluation, cross-validation, hyperparameter tuning, and model saving.

> **Note:** This project is developed for educational purposes and is not intended for medical diagnosis.

---

## 🎯 Objective

The project includes:

- Exploratory Data Analysis
- Missing value handling
- Categorical feature encoding
- Feature scaling
- Train-test splitting
- Logistic Regression
- Cross-validation
- Hyperparameter tuning using GridSearchCV
- Model evaluation
- Model saving and loading using Joblib

---

## 📂 Dataset

The project uses a **Heart Disease dataset based on the UCI Heart Disease dataset**.

The dataset contains **920 rows and 16 columns** with patient-related information such as:

- Age
- Sex
- Chest pain type
- Resting blood pressure
- Cholesterol
- Maximum heart rate
- Exercise-induced angina
- ST depression
- Slope
- Number of major vessels
- Thalassemia-related information

The original target column `num` contains multiple values. It was converted into a binary target:

```text
0 → No Heart Disease
1 → Heart Disease
```

Values greater than 0 were treated as the presence of heart disease.

---

## 🔄 Machine Learning Workflow

```text
Dataset
   ↓
Data Exploration
   ↓
Missing Value Handling
   ↓
Target Transformation
   ↓
Categorical Encoding
   ↓
Train-Test Split
   ↓
Feature Scaling
   ↓
Logistic Regression
   ↓
Model Evaluation
   ↓
Cross-Validation
   ↓
GridSearchCV
   ↓
Save & Load Model
```

---

## 🧹 Data Preprocessing

Missing values were checked using `isnull().sum()`.

- Numerical missing values were replaced using the **median**.
- Categorical missing values were replaced using the **mode**.
- Categorical features were converted into numerical features using **One-Hot Encoding**.
- `drop_first=True` was used to remove redundant categories.
- `StandardScaler` was used to scale the features.

The scaler was fitted only on the training data to avoid data leakage.

---

## 🤖 Model

### Logistic Regression

Logistic Regression was used because the project is a **binary classification problem**.

The model was trained using the training dataset and used to predict whether a patient belongs to the heart disease or no-heart-disease class.

---

## 📊 Evaluation

The model was evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- ROC Curve
- ROC-AUC

Five-fold cross-validation was also performed using `cross_val_score`.

`GridSearchCV` was used to tune Logistic Regression hyperparameters such as `C` and `solver`.

---

## 💾 Model Saving

The final trained model and feature scaler were saved using **Joblib**:

```text
heart_disease_model.pkl
heart_disease_scaler.pkl
```

The saved files were loaded again to verify that the model could be reused without retraining.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Joblib
- Jupyter Notebook

---

## 📁 Project Structure

```text
Week - 4/
│
├── MajorProject_Heart_Disease_Prediction.ipynb
├── heart_disease.csv
├── heart_disease_model.pkl
├── heart_disease_scaler.pkl
└── README.md
```

---

## 🚀 Future Improvements

- Compare Logistic Regression with Random Forest, SVM, and KNN.
- Perform further hyperparameter tuning.
- Apply feature selection techniques.
- Build an interactive prediction interface.
- Deploy the model as a web application.

---

## 👩‍💻 Author

**Sowmya Kolli**

**SkillNexis AI/ML Internship – Week 4**
