# Diabetes Prediction Pipeline

Simple machine learning pipeline using **Apache Airflow** and **Docker** to predict whether a patient is likely to have diabetes.

## Overview

This project builds an automated workflow that:

- loads the diabetes dataset
- preprocesses the data
- trains a Random Forest model
- evaluates the model
- saves the trained model

The pipeline runs inside Docker containers and is managed by Airflow.

## Project Structure

```text
Lab2/
├── dags/
│   ├── data/
│   │   └── diabetes_prediction_dataset.csv
│   ├── model/
│   │   └── diabetes_rf_model.sav
│   ├── src/
│   │   └── lab.py
│   └── airflow.py
├── logs/
├── plugins/
├── docker-compose.yaml
├── README.md
└── .env
```

## Requirements

Install or prepare:

- Docker Desktop
- Docker Compose
- at least 4GB memory for Docker

## How to Run

### 1. Set Airflow UID

```bash
echo -e "AIRFLOW_UID=$(id -u)" > .env
```

### 2. Create folders

```bash
mkdir -p dags logs plugins working_data
```

### 3. Initialize Airflow

```bash
docker compose up airflow-init
```

### 4. Start the services

```bash
docker compose up -d
```

### 5. Open Airflow UI

Go to:

```text
http://localhost:8080
```

Login:

- Username: `airflow2`
- Password: `airflow2`

## Pipeline Steps

The Airflow pipeline runs these tasks:

1. create model folder
2. load diabetes data
3. preprocess the dataset
4. train and save the model
5. evaluate model performance
6. print completion message

## Model Details

- **Model:** Random Forest Classifier
- **Target:** `diabetes`
- **Features:** gender, age, hypertension, heart_disease, smoking_history, bmi, HbA1c_level, blood_glucose_level

## Output

After running the pipeline, you get:

- a trained model file
- evaluation results in Airflow logs
- metrics such as accuracy and ROC-AUC

## Useful Commands

Trigger the pipeline from CLI:

```bash
docker compose exec airflow-cli airflow dags trigger Diabetes_Prediction_Pipeline
```

See running containers:

```bash
docker compose ps
```

Stop services:

```bash
docker compose down
```

## Dependencies

Main Python packages:

```text
pandas
numpy
scikit-learn
```

## Notes

- The model handles class imbalance using balanced class weights.
- Data scaling is applied before training.
- The trained model is saved in the `dags/model/` folder.

## References

- Apache Airflow
- Docker
- scikit-learn
- Diabetes Prediction Dataset
