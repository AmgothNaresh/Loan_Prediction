Loan Prediction Project

Overview
This project focuses on predicting whether a loan will be approved based on various features like applicant income, credit history, loan amount, etc. The pipeline includes data cleaning, exploratory data analysis (EDA), feature engineering, model building, evaluation, and improvement. The final goal is to build an accurate and interpretable model to assist financial institutions in automating loan approval decisions.

1. Data Cleaning

1.1 Loading Data
The dataset is loaded from a CSV file. It contains demographic, financial, and loan-related information for each applicant.

1.2 Handling Missing Values

Numerical features such as LoanAmount and Loan_Amount_Term are imputed using median.

Categorical features like Gender, Married, and Self_Employed are filled using the mode.

1.3 Encoding Categorical Variables

Binary categorical variables (e.g., Gender, Married) are encoded using Label Encoding.

Multi-class variables (e.g., Property_Area) are one-hot encoded.

1.4 Dropping Irrelevant Columns
The Loan_ID column is dropped as it does not contribute to prediction.

2. Exploratory Data Analysis (EDA)

2.1 Class Distribution
The dataset is imbalanced with more approved loans (Y) than rejected (N).

2.2 Univariate Analysis
Bar plots and histograms are used to understand individual feature distributions.

2.3 Bivariate Analysis
Relationships between loan status and features like income, credit history, and education are visualized.

2.4 Correlation Heatmap
A heatmap of numerical features shows how strongly features correlate with each other.

3. Feature Engineering

3.1 New Features
A new feature Total_Income is created by summing ApplicantIncome and CoapplicantIncome.

3.2 Log Transformation
Log transformation is applied on LoanAmount and Total_Income to reduce skewness.

4. Feature Selection

4.1 Feature Importance
Tree-based models such as Random Forest and AdaBoost are used to evaluate the importance of each feature in predicting loan approval.

5. Model Building

5.1 Train-Test Split
The dataset is split into training and testing sets.

5.2 Models Trained
Multiple models are trained and evaluated:

Support Vector Classifier (SVC)

K-Nearest Neighbors (KNC)

Multinomial Naive Bayes (MNB)

Decision Tree (DT)

Logistic Regression (LR)

Random Forest (RF)

AdaBoost Classifier (ABC)

Bagging Classifier (BgC)

Extra Trees Classifier (ETC)

Gradient Boosting Classifier (GBDT)

XGBoost Classifier (XGB)

5.3 Model Evaluation
Each model is evaluated using Accuracy and Precision.
AdaBoost gave the best performance with:

Accuracy: 86%

Precision: 86%

6. Cross-Validation
5-fold cross-validation on AdaBoost resulted in:

Scores: [0.813, 0.780, 0.780, 0.813, 0.795]

Average Accuracy: ~79.6%

7. Hyperparameter Tuning

Using GridSearchCV for AdaBoost:

Best Parameters: learning_rate = 0.5, n_estimators = 100

Best Cross-Validated Accuracy: ~79.6%

8. Feature Importance
AdaBoost’s feature importances were plotted to identify top contributing features like:

Credit_History

Total_Income

LoanAmount

9. Final Model and Deployment

9.1 Model Saving
The best-performing AdaBoost model is saved using joblib for future use:

9.2 Future Work

Use SMOTE to address class imbalance

Experiment with LightGBM and CatBoost

Improve model interpretability using SHAP/LIME

Deploy model using Streamlit or Flask

Set up a production-ready pipeline with CI/CD

Conclusion
This project demonstrates the end-to-end pipeline for a loan approval prediction system. Through EDA, feature engineering, model comparison, and hyperparameter tuning, we built a reliable model. With further improvements, this model can be deployed for real-world loan automation systems.# Loan_Prediction
