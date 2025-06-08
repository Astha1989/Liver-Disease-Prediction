# Indian Liver Disease Prediction

#### Goal: This project aims to build a binary classification model to predict whether an individual is likely to suffer from liver disease based on clinical attributes. The final solution integrates both a machine learning pipeline and a web-based deployment using Flask, HTML, and CSS.

### Dataset Overview:
The dataset is sourced from Kaggle, comprising:
     416 liver patients and 167 non-liver patients
     Data collected from Andhra Pradesh, India
     Each row represents a patient with features such as bilirubin levels, enzyme activity, protein levels, etc.
     The Dataset column serves as the target (1 = liver disease, 2 = no disease)

#### Features
Age
Gender
Total Bilirubin
Direct Bilirubin
Alkaline Phosphotase
Alamine Aminotransferase
Aspartate Aminotransferase
Total Proteins
Albumin
Albumin and Globulin Ratio
Dataset (Binary Target Variable)

### Project Pipeline
1. Exploratory Data Analysis (EDA)
Used countplots to verify class distribution — slightly imbalanced
Visualized feature distributions via histograms and boxplots
Applied correlation heatmaps to detect multicollinearity
Generated jointplots for important relationships (e.g., Albumin vs Total Proteins)

2. Feature Engineering
Replaced missing values in "Albumin_and_Globulin_Ratio" with mean
Encoded "Gender" as binary (Male = 1, Female = 0)
Used domain knowledge to impute other missing values (e.g., 0.94)
Dropped non-informative or redundant rows where necessary

3. Feature Selection
Selected features based on correlation and domain expertise:
Total_Bilirubin
Direct_Bilirubin
Alkaline_Phosphotase
Alamine_Aminotransferase
Total_Proteins
Albumin
Albumin_and_Globulin_Ratio

4. Model Building
Split the dataset into training and testing sets
Compared multiple supervised learning classifiers
Chose Logistic Regression for its robustness and performance
Also implemented Logistic Regression from scratch for learning purposes

5. Model Evaluation
Reported precision, recall, and F1-score for both classes
Emphasis placed on correctly identifying patients with liver disease (high recall)
Logistic Regression From Scratch
Implemented gradient descent manually
Used sigmoid activation for binary classification
Compared with sklearn implementation to validate learning
Achieved comparable accuracy on test data

6.Model Serialization
Trained model saved as .pkl file using joblib
Enables reuse in deployment without retraining

### Deployment Architecture: 
Backend: Flask (Python-based micro web framework)
Frontend: HTML + CSS
Model: Random Forest Classifier (via .pkl)
Files:
     app.py – Flask routing and inference logic
     liver.html – User input form
     result.html – Output result page
     Hosted locally on localhost:5000

### Sample of Application

#### Note: Focus was primarily on model logic and backend integration. Frontend kept minimal to prioritize functionality. Project serves as both a practical deployment example and a conceptual learning exercise.
