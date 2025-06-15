# 🏦 Loan Prediction Project

## 📌 Overview
This project focuses on predicting whether a loan will be approved or not based on applicant information. The pipeline includes data cleaning, exploratory data analysis (EDA), feature engineering, model training, evaluation, and hyperparameter tuning. The goal is to build an accurate and interpretable loan approval prediction model.

---

## 1. Data Cleaning

### 1.1 Loading Data
The dataset is loaded from a CSV file containing loan application records, including demographic, financial, and historical credit information.

### 1.2 Handling Missing Values
- Numerical columns like `LoanAmount` and `Loan_Amount_Term` are filled with the median.
- Categorical columns like `Gender`, `Married`, and `Self_Employed` are filled with the mode.

### 1.3 Encoding Categorical Variables
- Label Encoding is used for binary categories.
- One-Hot Encoding is used for multi-class categorical features (e.g., `Property_Area`, `Dependents`).

### 1.4 Converting Boolean Columns
Columns encoded as boolean (`True`/`False`) are converted into integers (`1`/`0`).

---

## 2. Exploratory Data Analysis (EDA)

### 2.1 Class Distribution
A countplot of `Loan_Status` reveals class imbalance—more approvals than rejections.

### 2.2 Univariate Analysis
Countplots and histograms used to understand distributions of categorical and numerical variables.

### 2.3 Bivariate Analysis
- Loan approval rates are compared across gender, marital status, and education levels.
- Income and loan amount distributions are compared between approved and non-approved loans.

### 2.4 Correlation Matrix
A heatmap of correlations between numerical variables is used to observe feature relationships.

---

## 3. Feature Engineering

### 3.1 Creating New Features
- `Total_Income = ApplicantIncome + CoapplicantIncome` created to represent the household income.

### 3.2 Log Transformation
Log transformation is applied to reduce skewness in `LoanAmount` and `Total_Income`.

---

## 4. Feature Selection

### 4.1 Dropping Irrelevant Columns
- Columns like `Loan_ID` are dropped as they don't contribute to prediction.

### 4.2 Using Feature Importance
Tree-based models like RandomForest and AdaBoost help identify important features based on model learning.

---

## 5. Model Building & Evaluation

### 5.1 Train-Test Split
The dataset is split into training and testing sets for unbiased model evaluation.

### 5.2 Models Trained
- Logistic Regression (LR)
- Decision Tree (DT)
- Random Forest (RF)
- Support Vector Classifier (SVC)
- K-Nearest Neighbors (KNC)
- Multinomial Naive Bayes (NB)
- AdaBoost Classifier (ABC)
- Bagging Classifier (BgC)
- Extra Trees Classifier (ETC)
- Gradient Boosting (GBDT)
- XGBoost Classifier (XGB)

### 5.3 Evaluation Metrics
Each model is evaluated using:
- **Accuracy**
- **Precision**
- **Confusion Matrix**
- **Classification Report**

### 5.4 Final Model Selection
- **AdaBoost Classifier** chosen based on accuracy and precision:
  - Accuracy: ~86%
  - Precision: ~86%

---

## 6. Cross-Validation

Used `cross_val_score()` with 5-fold CV:
```python
Cross-validation Scores: [0.813, 0.780, 0.780, 0.813, 0.795]
Average Accuracy: ~79.6%
