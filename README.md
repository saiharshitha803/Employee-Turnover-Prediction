# Employee-Turnover-Prediction
 Employee Turnover Prediction Model
 
>>> Project Overview

Employee turnover (attrition) is one of the biggest challenges organizations face. High turnover can result in:
Increased recruitment and training costs
Loss of organizational knowledge
Decreased employee morale and productivity
This project leverages Machine Learning (ML) to predict whether an employee is likely to stay (0) or leave (1) the company,
based on their historical HR data (performance, workload, satisfaction, promotions, etc.).
By using this model, HR teams and managers can identify at-risk employees early and take proactive measures such as career development plans,
workload balancing, or targeted retention strategies.

>> Objectives

Analyze employee HR data to identify factors influencing turnover.
Select the most relevant features using Recursive Feature Elimination (RFE).
Train a robust Random Forest model for turnover prediction.
Provide a prediction pipeline that works with new employee records in real time.

>> Dataset

The dataset used for training is HR_Data_Predict Employee Turnover.csv.
Columns in Dataset:
satisfaction_level → Job satisfaction (0–1 scale)
last_evaluation → Last performance evaluation score (0–1)
number_project → Number of projects handled
average_montly_hours → Average monthly working hour
time_spend_company → Years spent at the company
Work_accident → Whether employee had an accident (0/1)
promotion_last_5years → Whether employee was promoted in last 5 years (0/1)
Department → Department name (sales, accounting, support, IT, etc.)
salary → Salary level (low/medium/high)
left → Target variable (0 = Stayed, 1 = Left)
⚠️ Categorical values (Department, salary) are encoded before training.

>> Methodology

🔹 Step 1: Data Preprocessing
Consolidate IT and support departments into technical (to reduce redundancy).
One-Hot Encode categorical features (Department, salary).
Drop irrelevant columns (left used as target).

🔹 Step 2: Feature Selection
Use Logistic Regression + RFE (Recursive Feature Elimination) to select the 10 most important features.
This ensures the model focuses only on the strongest predictors of turnover.

🔹 Step 3: Model Training
Train a Random Forest Classifier using the selected features.
Chosen because Random Forests handle non-linear relationships well and are less sensitive to scaling.

🔹 Step 4: Prediction Pipeline
Accept new employee records as a Python dictionary or DataFrame.
Apply the same preprocessing steps as the training dataset (encoding, feature alignment, scaling).
Predict the likelihood of leaving with both binary classification (0/1) and probability score (0–1).

>> Interpretation

Prediction = 1 → Employee is at high risk of leaving.
Prediction = 0 → Employee is likely to stay.
Probability_of_Leaving helps measure confidence (e.g., 92% risk vs. 8% risk).
