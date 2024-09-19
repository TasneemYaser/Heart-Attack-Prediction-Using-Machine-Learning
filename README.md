# Overview
This project aims to predict the likelihood of heart attacks using a combination of dimensionality reduction, feature selection, and various machine learning models. Specifically, we employ Linear Discriminant Analysis (LDA) for dimensionality reduction and Particle Swarm Optimization (PSO) for feature selection. Two primary classifiers are used for prediction: Logistic Regression and Random Forest, ensuring a comprehensive evaluation of model performance. The project’s goal is to develop an efficient, accurate system for predicting heart attacks using clinical data.
# Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Data Preprocessing](#data-preprocessing)
  - [Dimensionality Reduction with LDA](#dimensionality-reduction-with-lda)
  - [Feature Selection with PSO](#feature-selection-with-pso)
  - [Model Training](#model-training)
- [Evaluation and Results](#evaluation-and-results)
  - [Logistic Regression](#logistic-regression)
  - [Random Forest Classifier](#random-forest-classifier)
  - [Visualization](#visualization)
- [Conclusion](#conclusion)
- [Usage](#usage)
- [Future Work](#future-work)
- [License](#license)
# Dataset
The dataset used for this project is the [Heart Attack Analysis and Prediction Dataset](https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset) from Kaggle. It contains 14 features that represent medical and demographic attributes of patients, which are critical indicators of heart attack risk. The dataset is made up of the following key attributes:

- Age: The age of the patient.
- Sex: Gender of the patient (1 = Male, 0 = Female).
- Chest Pain Type (cp): Ranges from 0 to 3, where different values correspond to various types of chest pain.
- Resting Blood Pressure (trestbps): Resting blood pressure in mm Hg on admission to the hospital.
- Cholesterol (chol): Serum cholesterol in mg/dl.
- Fasting Blood Sugar (fbs): Indicates if fasting blood sugar is higher than 120 mg/dl (1 = true, 0 = false).
- Resting Electrocardiographic Results (restecg): Values indicating normalcy or abnormality of the ECG.
- Max Heart Rate Achieved (thalach): Maximum heart rate achieved during the exercise test.
- Exercise-Induced Angina (exang): Indicates if the patient has experienced exercise-induced angina (1 = yes, 0 = no).
- Oldpeak: ST depression induced by exercise relative to rest.
- Slope: The slope of the peak exercise ST segment.
- Number of Major Vessels (ca): Number of major vessels (0-3) colored by fluoroscopy.
- Thalassemia (thal): Blood disorder (0 = normal, 1 = fixed defect, 2 = reversible defect).
- Target: 0 = No heart disease, 1 = Heart disease.
The dataset has a binary target, indicating the presence or absence of heart disease. It includes 303 records, which were split into training and test sets to evaluate model performance.
# Methodology
## Data Preprocessing
  1-Shuffling & Splitting: The dataset is shuffled to ensure a balanced distribution of samples. The dataset is then split into feature 
   inputs (X) and output labels (y).
  2-Scaling: StandardScaler is applied to normalize feature values, ensuring that all features are on the same scale, with a mean of 0 
   and a standard deviation of 1.
