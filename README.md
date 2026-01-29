📉 Predicting Employee Retention: Salifort Motors

Authors: Chinmay H R, Vishnu Vardhan Chedella, Tran Dieu Anh

Project Type: HR Analytics / Classification Modeling

Status: Completed

📌 Project Overview
The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction and retention levels. They collected data from employees, but now they don’t know what to do with it. They refer to you as a data analytics professional and ask you to provide data-driven suggestions based on your understanding of the data.

Goal: Analyze the key drivers of employee turnover and build a machine learning model to predict whether an employee will leave the company. This enables the organization to intervene early and retain valuable talent.

📂 Repository Structure
Predicting_Employee_Retention_Starter...ipynb: The main Jupyter Notebook containing the full data science pipeline (Data cleaning, EDA, Feature Engineering, Modeling).

Predicting_Employee_Retention_Report.pdf: Executive summary and detailed report of findings.

README.md: Project summary and instructions.

🛠️ Technologies & Libraries
The project is implemented in Python using the following ecosystem:

Data Manipulation: pandas, numpy

Visualization: matplotlib.pyplot, seaborn

Machine Learning: scikit-learn (sklearn), xgboost

Models: LogisticRegression, RandomForestClassifier, XGBClassifier

Metrics: accuracy_score, precision_score, recall_score, f1_score, confusion_matrix, classification_report, roc_auc_score

Utility: pickle (for model saving)

⚙️ Project Pipeline
1. Data Understanding & Cleaning
The dataset consists of approximately 15,000 employee records with 10 features.

Cleaning: Checked for missing values and duplicates.

Renaming: Standardized column names for better readability (e.g., average_montly_hours to avg_monthly_hours).

Outlier Handling: Identified outliers in tenure (time_spend_company) but retained them as they represented valid data points for senior employees.

2. Exploratory Data Analysis (EDA)
Comprehensive analysis was performed to identify trends:

Turnover Rate: Approximately 16.6% of employees in the dataset had left the company.

Satisfaction: Employees who left had significantly lower satisfaction scores compared to those who stayed.

Workload: A bimodal distribution was observed for those who left:

Overworked: Employees working 250+ hours/month.

Underutilized: Employees working <150 hours/month.

Tenure: Attrition peaks at year 3 and year 4.

3. Model Building
Two main modeling approaches were tested: Logistic Regression and Tree-Based Models (Random Forest & XGBoost).

A. Logistic Regression
Used as a baseline for interpretability.

Results: precision: 80%, recall: 83%, f1-score: 81%, accuracy: 82%.

Note: While effective, it assumed linear relationships which might not capture complex interaction effects (e.g., burnout loops).

B. Random Forest Classifier (Champion Model)
Cross-Validation: Tuned using GridSearchCV to optimize hyperparameters (max_depth, min_samples_leaf, min_samples_split, n_estimators).

Performance:

Accuracy: 98.5%

Precision: 99.2%

Recall: 91.5%

F1 Score: 95.2%

AUC: 98.1%

The Random Forest model significantly outperformed Logistic Regression, proving that the relationships between workload, satisfaction, and turnover are non-linear.

🔍 Key Findings & Insights
The Random Forest model identified the following as the most critical features driving retention:

Satisfaction Level: The strongest predictor. Low satisfaction correlates directly with turnover.

Number of Projects: Employees with very few (2) or very many (7) projects are most likely to leave. The "sweet spot" is 3-5 projects.

Tenure: Employees at the 4-year mark are at high risk, likely due to lack of promotion or burnout.

Overworked High Performers: A specific cluster of employees with high evaluation scores but excessive hours (>175/month) are leaving, indicating burnout.

🚀 Recommendations for Management
Based on the analysis, the following actions are recommended to Salifort Motors:

Cap Work Hours: Limit the number of projects per employee to prevent burnout (max 5 projects).

Promotion Review: Investigate why employees around the 4-year mark are leaving. If it's a lack of growth, implement a clearer promotion path.

Reward High Performers: Employees with high evaluation scores who work long hours are flight risks. Consider "stay interviews" or compensation adjustments for this group.

Clarify Roles: For employees with low hours and low project counts, investigate if training or role realignment is needed.
