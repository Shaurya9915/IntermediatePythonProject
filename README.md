Project Title

Credit Risk Segmentation and Exploratory Data Analysis on German Credit Dataset

Objective

This project aims to analyze customer credit behavior using the German Credit dataset. 
It includes exploratory data analysis (EDA), missing value handling, risk segmentation, and clustering to uncover patterns that can inform credit risk strategies.

Dataset Overview

Source: german_credit_data.csv

Rows: 1000

Columns: 10

Key Features:

Age, Sex, Job, Housing

Saving accounts, Checking account

Credit amount, Duration, Purpose

Exploratory Data Analysis (EDA)

Checked for missing values:

Saving accounts: 18.7% missing

Checking account: 39.4% missing

Imputed missing values with 'unknown' for categorical columns.

Descriptive statistics for Age and Credit amount

Group-wise analysis:

Mean age by Sex

Mean credit amount by Housing

Credit trends by Duration

Correlation matrix for numeric features

Risk Segmentation Logic

High Risk Flag: Customers with Credit amount > 90th percentile

threshold = df["Credit amount"].quantile(0.90)
df["high_risk_flag"] = (df["Credit amount"] > threshold).astype(int)

Distribution of high-risk customers using value_counts(normalize=True)

Clustering (KMeans)

Features used: Age, Credit amount, Duration

Applied KMeans with n_clusters=3, random_state=42, n_init="auto"

Cluster labels stored in risk_cluster

Warning-free implementation:

from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=3, random_state=42, n_init="auto")
df["risk_cluster"] = kmeans.fit_predict(df_encoded[["Age", "Credit amount", "Duration"]])

Visualizations

Histogram of Age distribution (bins=30)

Cluster-wise average credit amount and duration

Purpose-wise credit distribution

Business Impact

Identifies high-risk customers for targeted credit policies

Enables segmentation for personalized financial products

Supports fraud detection and credit scoring models

Tech Stack

Python, Pandas, NumPy

Matplotlib, Seaborn

scikit-learn (KMeans)

Jupyter Notebook
