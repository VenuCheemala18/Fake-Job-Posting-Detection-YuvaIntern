# Fake Job Posting Detection 🚨

## 📌 Project Overview

Fake job postings are a serious problem for job seekers and recruitment platforms. Fraudulent job advertisements can mislead applicants, collect personal information, or cause financial loss.

This project develops an end-to-end Data Science workflow for detecting potentially fraudulent job postings using data cleaning, exploratory data analysis, advanced visualization, statistical analysis, hypothesis testing, machine learning, model evaluation, and strategic recommendations.

The project was completed as a 5-week Data Science project.

---

# 🎯 Project Objective

The main objectives of this project are:

- Analyze fake job posting data
- Clean and preprocess the dataset
- Perform exploratory data analysis
- Identify patterns in genuine and fraudulent job postings
- Create meaningful visualizations
- Perform statistical analysis and hypothesis testing
- Build a machine learning classification model
- Evaluate the model using multiple performance metrics
- Generate business insights
- Provide strategic recommendations for fake-job detection

---

# 📅 Week 1 — Data Acquisition, Cleaning & Exploratory Data Analysis

## Objectives

- Load and inspect the dataset
- Understand dataset structure
- Analyze missing values
- Check duplicate records
- Validate data types
- Handle missing values
- Prepare the target variable
- Perform exploratory data analysis
- Create derived features

## Dataset

The cleaned dataset initially contained:

- 6,841 records
- 19 columns
- 6,525 genuine job postings
- 315 fraudulent job postings
- 1 record with a missing target value

After removing the record with the missing target value, the final labeled dataset contained 6,840 job postings.

## Important Columns

- job_id
- title
- location
- department
- salary_range
- company_profile
- description
- requirements
- benefits
- telecommuting
- has_company_logo
- has_questions
- employment_type
- required_experience
- required_education
- industry
- function
- fraudulent
- description_length

## Data Cleaning

The following preprocessing activities were performed:

- Missing-value analysis
- Duplicate-record checking
- Handling missing text and categorical values
- Removal of records with missing target values
- Data-type validation
- Dataset structure validation

## Feature Engineering

A new feature was created:

`description_length`

This feature represents the length of the job description and provides an additional signal for analysis and machine learning.

## Exploratory Data Analysis

The dataset was explored to understand:

- Genuine vs fraudulent job postings
- Missing-value patterns
- Job description length
- Employment-related characteristics
- Company logo presence
- Telecommuting information

---

# 📊 Week 2 — Advanced Data Visualization & Data Storytelling

## Objectives

Week 2 focused on analyzing fraud patterns through advanced visualizations and communicating the findings clearly.

## Visualizations

The following visualizations were created:

1. Fraud Rate by Employment Type
2. Fraud Rate by Required Experience
3. Fraud Rate by Required Education
4. Fraud Rate by Industry
5. Fraud Rate by Company Logo Presence
6. Correlation Heatmap

## Key Findings

- Fraudulent job postings represent a small percentage of the dataset.
- Fraud rates vary across employment types.
- Fraud rates differ across experience levels.
- Education requirements show differences in fraud rates.
- Some industries show different levels of fraudulent activity.
- Company logo presence can provide a potentially useful signal.
- Correlation analysis helps identify relationships among numerical variables.

For industry-level analysis, groups with very small numbers of postings were avoided where appropriate to reduce unstable fraud-rate estimates.

## Business Insight

Fake-job detection should not depend on a single characteristic. Multiple job-posting attributes can be combined to identify potentially suspicious postings.

---

# 📈 Week 3 — Statistical Analysis & Hypothesis Testing

## Objectives

Week 3 focused on determining whether selected job-posting characteristics were statistically associated with fraudulent job status.

## Statistical Method

The Chi-Square Test of Independence was used for categorical variables.

## Hypotheses

### Null Hypothesis (H₀)

There is no significant association between the selected categorical variable and fraudulent job status.

### Alternative Hypothesis (H₁)

There is a significant association between the selected categorical variable and fraudulent job status.

## Test 1 — Company Logo vs Fraud

Chi-Square Statistic:

`258.8468`

p-value:

`3.0611e-58`

Degrees of Freedom:

`1`

Fraud Rates:

- With Company Logo: approximately 2.39%
- Without Company Logo: approximately 12.19%

The result is statistically significant at α = 0.05.

## Test 2 — Screening Questions vs Fraud

Chi-Square Statistic:

`56.1890`

p-value:

`6.5829e-14`

Degrees of Freedom:

`1`

Fraud Rates:

- Without Questions: approximately 6.68%
- With Questions: approximately 2.84%

The result is statistically significant at α = 0.05.

## Test 3 — Telecommuting vs Fraud

Chi-Square Statistic:

`5.5049`

p-value:

`0.01896`

Degrees of Freedom:

`1`

The result is statistically significant at α = 0.05.

## Statistical Conclusion

The hypothesis tests indicate statistically significant associations between fraudulent job status and the selected categorical variables.

However, statistical association does not imply causation.

---

# 🤖 Week 4 — Machine Learning Model Development & Evaluation

## Objective

The objective of Week 4 was to develop a machine learning classification model to predict whether a job posting is genuine or fraudulent.

## Machine Learning Model

Logistic Regression was used as the baseline classification model.

## Features Used

### Numerical Features

- telecommuting
- has_company_logo
- has_questions
- description_length

### Categorical Features

- employment_type
- required_experience
- required_education

## Data Preprocessing

The machine learning pipeline included:

- Median imputation for numerical features
- Most-frequent imputation for categorical features
- StandardScaler for numerical features
- OneHotEncoder for categorical features
- ColumnTransformer for combining preprocessing steps
- Logistic Regression classifier

## Handling Class Imbalance

The dataset contains significantly more genuine postings than fraudulent postings.

Therefore, the Logistic Regression model was configured using:

`class_weight="balanced"`

This gives additional importance to the minority fraudulent class.

## Train-Test Split

- Training data: 80%
- Testing data: 20%
- Random State: 42
- Stratified split: Yes

## Model Performance

| Metric | Score |
|---|---:|
| Accuracy | 74.49% |
| Precision | 11.76% |
| Recall | 69.84% |
| F1-Score | 20.14% |
| ROC-AUC | 82.06% |

## Confusion Matrix

| | Predicted Genuine | Predicted Fraudulent |
|---|---:|---:|
| Actual Genuine | 975 | 330 |
| Actual Fraudulent | 19 | 44 |

## Model Interpretation

Because the dataset is highly imbalanced, accuracy alone is not sufficient for evaluating the model.

The ROC-AUC score of approximately 0.82 indicates useful discriminatory ability.

The fraudulent-class recall of approximately 69.84% shows that the model identified a substantial portion of fraudulent postings.

However, the precision of approximately 11.76% is low, meaning that many postings predicted as fraudulent were actually genuine.

---

# 🧠 Week 5 — Comprehensive Fake Job Posting Detection Project

Week 5 integrated the complete project workflow into one comprehensive Fake Job Posting Detection project.

## End-to-End Workflow

```text
Data Acquisition
       ↓
Data Cleaning
       ↓
Exploratory Data Analysis
       ↓
Advanced Visualization
       ↓
Statistical Analysis
       ↓
Hypothesis Testing
       ↓
Machine Learning
       ↓
Model Evaluation
       ↓
Strategic Recommendations
       ↓
Future Improvements

👨‍💻 Author
Venu Cheemala

M.C.A

Skills Demonstrated

Python
SQL
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
EDA
Data Cleaning
Data Visualization
Statistical Analysis
Hypothesis Testing
Machine Learning
Model Evaluation
Data Science
