# DiabetesPrediction

https://www.kaggle.com/datasets/saurabh00007/diabetescsv

The link for Diabetes Prediction

Diabetes Prediction using Support Vector Machine (SVM)
This repository contains a machine learning project designed to predict diabetes in patients based on several clinical measurements. The model is built using a Support Vector Machine (SVM) classifier with a linear kernel, trained on the Pima Indians Diabetes Dataset.

Table of Contents
Project Overview
Dataset Description
Model Architecture & Pipeline
Performance & Evaluation
Installation & Requirements
How to Use
Contributing
Project Overview
Diabetes is a major chronic disease worldwide. Early detection can lead to lifestyle interventions and treatment that prevent severe complications. This project demonstrates a complete workflow to preprocess clinical data, standardize features, train an SVM model, and use it to predict whether a patient has diabetes.

Dataset Description
The dataset used contains several clinical parameters for female patients of Pima Indian heritage:

Pregnancies: Number of times pregnant
Glucose: Plasma glucose concentration (2 hours in an oral glucose tolerance test)
BloodPressure: Diastolic blood pressure (mm Hg)
SkinThickness: Triceps skin fold thickness (mm)
Insulin: 2-Hour serum insulin (mu U/ml)
BMI: Body mass index (weight in kg/(height in m)^2)
DiabetesPedigreeFunction: A score indicating the likelihood of diabetes based on family history
Age: Age in years
Outcome: Class variable (0 = Non-Diabetic, 1 = Diabetic)
Model Architecture & Pipeline
Data Standardization: Features are scaled using StandardScaler to ensure the SVM algorithm converges optimally, as SVM is highly sensitive to feature scales.
Data Splitting: Stratified splitting (train_test_split) is applied to maintain the ratio of diabetic to non-diabetic cases across training (80%) and testing (20%) sets.
Classifier: A Support Vector Classifier (SVC) with a linear kernel is utilized to model the decision boundary.
Performance & Evaluation
Training Accuracy: ~78.66%
Test Accuracy: ~77.27%
Installation & Requirements
To run this project locally, ensure you have Python installed, then install the necessary dependencies:

pip install numpy pandas scikit-learn
How to Use
You can predict diabetes for a new patient by passing their clinical parameters to the trained classifier pipeline:

import numpy as np

# Order of features: Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age
input_data = (8, 183, 64, 0, 0, 23.3, 0.672, 32)

# Convert to numpy array and reshape
input_data_reshaped = np.asarray(input_data).reshape(1, -1)

# Standardize using the fitted scaler
std_data = scaler.transform(input_data_reshaped)

# Predict
prediction = classifier.predict(std_data)

if prediction[0] == 0:
    print('The person is not diabetic')
else:
    print('The person is diabetic')
Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page or submit a pull request.
