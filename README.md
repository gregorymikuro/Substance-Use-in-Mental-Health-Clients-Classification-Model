
# Substance Use in Mental Health Clients Classification Model

## Overview


![image](https://github.com/gregorymikuro/Substance-Use-in-Mental-Health-Clients-Classification-Model/assets/155205164/1c4e210e-b02b-4d3a-954a-4303da4660ae)


This project aims to develop a machine learning model that can identify mental health clients with a higher risk of substance abuse problems (SAP). The model utilizes a combination of the client's primary mental health diagnosis and demographic information to predict their SAP status. The data is sourced from SAMHSA.

## Project Structure

This project is organized into the following components, implemented as Python classes for modularity and reusability:

1. **Data Extractor:** Loads and combines raw data.
2. **Data Cleaning:** Cleans and prepares data for analysis.
3. **Exploratory Data Analysis (EDA):** Examines data distributions, relationships, and visualizations.
4. **Modeling:** Trains and evaluates various machine learning models.
5. **Evaluation:** Assesses model performance and selects the best-performing one(s).

## Business Understanding

### Problem Statement
Substance abuse is a significant concern among mental health clients. Identifying clients at higher risk for substance abuse can help healthcare providers offer timely interventions and support.

### Objectives
- Develop a predictive model to classify mental health clients based on their risk of substance abuse problems.
- Identify key factors influencing substance abuse risk to inform intervention strategies.

### Proposed Solution
A machine learning classifier will be trained on historical data to predict the SAP status of mental health clients. We aim for an accuracy score of at least 80%.

### Metrics
- Accuracy
- Precision
- Recall
- F1-Score

### Conclusion
By identifying clients at risk for substance abuse, the project aims to improve mental health care delivery and enhance client outcomes.

## Data Understanding

### Source
The dataset was obtained from the Substance Abuse and Mental Health Services Administration (SAMHSA).

### Datasets
- **CSV File:** `mhcld_puf_2022.csv` inside `data/MH-CLD-2022-DS0001-bndl-data-csv_v1.zip`.

### Columns (Key Features)
- **Target Variable:**
  - `SAP` (Substance Abuse Problem)
- **Predictor Variables:**
  - **Primary Mental Health Condition:**
    - `MH1` (Exclude values indicating substance use disorders - value 12)
  - **Demographic Variables:**
    - `AGE` (Client Age)
    - `ETHNIC` (Client Ethnicity)
    - `RACE` (Client Race)
    - `GENDER` (Client Gender)
    - `MARSTAT` (Marital Status)
    - `EDUC` (Client Education)
    - `EMPLOY` (Employment Status)
    - `LIVARAG` (Living Arrangement)
    - `VETERAN` (Veteran Status)
    - `STATEFIP` (State FIPS Code)

## Data Cleaning and Preparation
- Extracted data from the ZIP file and selected required columns.
- Renamed columns to be more intuitive:
  - `SAP` -> `target-variable`
  - `MH1` -> `primary-mental-health-condition`
  - `AGE` -> `age`
  - `ETHNIC` -> `ethnicity`
  - `RACE` -> `race`
  - `GENDER` -> `gender`
  - `MARSTAT` -> `marital-status`
  - `EDUC` -> `education`
  - `EMPLOY` -> `employment-status`
  - `LIVARAG` -> `living-arrangement`
  - `VETERAN` -> `veteran-status`
  - `STATEFIP` -> `state-fips-code`
- Saved the cleaned data to `data/extracted-data.csv`.

## Exploratory Data Analysis (EDA)
- **Univariate Analysis:** Examined distributions of individual features.
- **Bivariate Analysis:** Assessed correlations between numerical features and categorical features using visualizations.
- **Multivariate Analysis:** Analyzed relationships between multiple variables and the target variable.

## Modeling and Evaluation

### Models
1. Logistic Regression
2. Decision Tree
3. Random Forest
4. LightGBM
5. CatBoost
6. XGBoost
7. Voting Classifier (Ensemble of top 3 models)

### Evaluation
- Used accuracy, confusion matrix, and classification report for evaluation.
- Identified the Voting Classifier as the best-performing model with an accuracy of over 80%.

## Conclusion and Recommendations
The Voting Classifier performed best, achieving an accuracy level of over 80%. The models demonstrate promise in predicting substance abuse risk among mental health clients. Future work includes refining the models, exploring advanced feature engineering techniques, and deploying the model in a user-friendly application for healthcare providers.

