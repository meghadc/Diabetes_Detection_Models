
# Data Science in Microsoft Fabric

This project demonstrates a complete data science workflow using Microsoft Fabric, leveraging Azure storage, Spark, and machine learning libraries. The primary objective is to perform linear regression and classification on a diabetes dataset.

## Project Overview
The code is organized into the following steps:

### 1. Data Access and Loading
* Connects to Azure Blob Storage using anonymous access.
* Configures Spark to read Parquet data from Azure using the wasbs:// protocol.
* Displays the loaded DataFrame using display(df).
* Converts the Spark DataFrame to a Pandas DataFrame using .toPandas().

### 2. Data Cleaning and Feature Engineering
* A custom function clean_data() is used to create a new column, Risk, based on a threshold value.
* The Risk column indicates whether a patient has a higher likelihood of diabetes.
* Summary statistics of the cleaned data are displayed using df_clean.describe().

### 3. Train-Test Split
* The features (AGE, SEX, BMI, BP, S1, S2, S3, S4, S5, S6) and the target variable (Y) are separated.
* The data is split into training and testing sets using train_test_split.

### 4. Experiment Tracking with MLflow
* mlflow is used to track the experiment.
* A new experiment named diabetes-regression is created using mlflow.set_experiment().

### 5. Model Training
* A Linear Regression model is trained using LinearRegression().
* A Classification model is also implemented to predict the Risk column.
* mlflow.autolog() is enabled to automatically log model parameters, metrics, and artifacts.

## Requirements
Ensure the following packages are installed:
* Python 3.8+
* pandas
* numpy
* pyspark
* sklearn
* mlflow
* azure-storage-blob

## How to Run
* Configure Azure Blob Storage access.
* Ensure Microsoft Fabric and Spark environments are set up.
* Run the Jupyter Notebook or Python script step by step.
* Monitor the experiment results in the MLflow UI.

