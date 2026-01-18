Project Title

Diabetic Patient Readmission Analysis – Hospital Risk Profiling

Objective

This project analyzes hospital readmission patterns among diabetic patients. The goal is to identify age groups and admission types associated with higher readmission rates, clean and prepare the dataset, and support hospital-level decision-making.

Dataset Overview

Source: diabetic_data.csv

Rows: ~100,000

Columns: 50

Key Features:

encounter_id, patient_nbr, race, gender, age, weight

admission_type_id, discharge_disposition_id, admission_source_id

time_in_hospital, readmitted (target variable)

Key Analysis Steps

Loaded and inspected the dataset

Target variable readmitted has three categories: NO, >30, <30

Calculated readmission distribution and normalized proportions

Dropped irrelevant columns: patient_nbr, readmitted (for feature selection)

Handled missing values:

Dropped weight due to excessive nulls

Filled remaining nulls with 'Unknown'

Analyzed age distribution and visualized with countplot

Created crosstab of age vs readmission status

Insights

Majority of patients fall in age brackets [60-70), [70-80), and [50-60)

Readmission rate:

NO: 60.5%

>30 days: 26.6%

<30 days: 11.4%

Age group [70-80) has highest patient count

Crosstab shows younger patients have slightly higher short-term readmission rates

Business Impact

Helps hospitals identify high-risk age groups for readmission

Supports targeted discharge planning and follow-up strategies

Enables better resource allocation for diabetic care units

Tools Used

Python, Pandas

Matplotlib, Seaborn

Jupyter Notebook
