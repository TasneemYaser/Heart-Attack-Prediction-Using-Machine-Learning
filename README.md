# Overview
This project aims to predict the likelihood of heart attacks using a combination of dimensionality reduction, feature selection, and various machine learning models. Specifically, we employ Linear Discriminant Analysis (LDA) for dimensionality reduction and Particle Swarm Optimization (PSO) for feature selection. Two primary classifiers are used for prediction: Logistic Regression and Random Forest, ensuring a comprehensive evaluation of model performance. The project’s goal is to develop an efficient, accurate system for predicting heart attacks using clinical data.
# Table of Contents

- [Overview](#project)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Data Preprocessing](#data-preprocessing)
  - [Dimensionality Reduction with LDA](#dimensionality-reduction-with-lda)
  - [Feature Selection with PSO](#feature-selection-with-pso)
  - [Model Training](#model-training)
- [Evaluation and Results](#evaluation-and-results)
  - [Logistic Regression](#logistic-regression)
  - [Random Forest Classifier](#random-forest-classifier)
- [Conclusion](#conclusion)
# Dataset
The dataset used for this project is the [Heart Attack Analysis and Prediction Dataset](https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset) from Kaggle. It contains 14 features that represent medical and demographic attributes of patients, which are critical indicators of heart attack risk. The dataset is made up of the following key attributes:

- **Age:** The age of the patient.
- **Sex:** Gender of the patient (1 = Male, 0 = Female).
- **Chest Pain Type (cp):** Ranges from 0 to 3, where different values correspond to various types of chest pain.
- **Resting Blood Pressure (trestbps):** Resting blood pressure in mm Hg on admission to the hospital.
- **Cholesterol (chol):** Serum cholesterol in mg/dl.
- **Fasting Blood Sugar (fbs):** Indicates if fasting blood sugar is higher than 120 mg/dl (1 = true, 0 = false).
- **Resting Electrocardiographic Results (restecg):** Values indicating normalcy or abnormality of the ECG.
- **Max Heart Rate Achieved (thalach):** Maximum heart rate achieved during the exercise test.
- **Exercise-Induced Angina (exang):** Indicates if the patient has experienced exercise-induced angina (1 = yes, 0 = no).
- **Oldpeak:** ST depression induced by exercise relative to rest.
- **Slope:** The slope of the peak exercise ST segment.
- **Number of Major Vessels (ca):** Number of major vessels (0-3) colored by fluoroscopy.
- **Thalassemia (thal):** Blood disorder (0 = normal, 1 = fixed defect, 2 = reversible defect).
- **Target:** 0 = No heart disease, 1 = Heart disease.
The dataset has a binary target, indicating the presence or absence of heart disease. It includes 303 records, which were split into training and test sets to evaluate model performance.
# Methodology
## Data Preprocessing
  1-Shuffling & Splitting: The dataset is shuffled to ensure a balanced distribution of samples. The dataset is then split into feature 
   inputs (X) and output labels (y).
   
  2-Scaling: StandardScaler is applied to normalize feature values, ensuring that all features are on the same scale, with a mean of 0 
   and a standard deviation of 1.
## Dimensionality Reduction with LDA
Linear Discriminant Analysis (LDA) is applied to reduce the dimensionality of the feature set. LDA finds the most significant features that contribute to class separability, which helps prevent overfitting and improves model interpretability. The reduced feature set retains the most critical information necessary for classification.
## Feature Selection with PSO
We use Particle Swarm Optimization (PSO) for feature selection. PSO, inspired by the social behavior of birds flocking or fish schooling, optimizes the selection of the most relevant features from the LDA-reduced dataset. The goal is to improve the model's performance by selecting a subset of features that yield the best accuracy while minimizing complexity.

## Model Training
Two classifiers were trained and evaluated on the selected features:

1-Logistic Regression: Implemented to establish a baseline for performance comparison. This algorithm helps in understanding the relationships between features and the target label.
2-Random Forest Classifier: A robust ensemble method that combines multiple decision trees to improve classification accuracy and handle non-linear relationships between features.
Each classifier was trained on the selected features from PSO and evaluated using a test dataset.
## Evaluation and Results
This section presents the performance evaluation of the models used in the project. Both Logistic Regression and Random Forest Classifier were applied to predict heart attack risk. Logistic Regression was implemented in two ways: manually (from scratch) and using the scikit-learn library. Additionally, the scikit-learn Random Forest was evaluated for comparison.

1. Logistic Regression:
**Metrics:**
**Accuracy:** The manually implemented model achieved an accuracy of **85.24%**, providing a benchmark for comparison with more complex models.
**Confusion Matrix:** A confusion matrix was used to assess the model's performance in predicting heart attack risk. It reveals the distribution of true positives, false positives, true negatives, and false negatives, offering valuable insights into the model's classification capabilities.
**Classification Report:** A detailed classification report was generated, displaying key metrics such as precision, recall, and F1-score for each class. This breakdown highlights the model's strengths and weaknesses in handling heart attack predictions.
2. Random Forest Classifier (scikit-learn)
**Metrics:**
**Accuracy:** The Random Forest model achieved the highest accuracy of **86.88%**, outperforming both logistic regression models and showing its suitability for handling complex patterns in the dataset.
## Conclusion
This project demonstrates how combining dimensionality reduction (LDA) and feature selection (PSO) can enhance machine learning models' performance. By integrating these techniques, we improved the predictive accuracy of traditional classifiers such as Logistic Regression and Random Forest. The success of the project highlights the importance of selecting relevant features and reducing dimensionality when dealing with high-dimensional medical data.
