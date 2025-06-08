# Indian Liver Disease Prediction

#### Goal: This project aims to build a binary classification model to predict whether an individual is likely to suffer from liver disease based on clinical attributes. The final solution integrates both a machine learning pipeline and a web-based deployment using Flask, HTML, and CSS.

### Dataset Overview:
The dataset used in this project is sourced from Kaggle and consists of 416 records of patients diagnosed with liver disease and 167 records of patients without liver disease. The data was collected from the North East region of Andhra Pradesh, India. Each row in the dataset represents a patient and includes clinical features such as bilirubin levels, enzyme concentrations, and protein measures. The Dataset column is the target variable, where the value 1 indicates the presence of liver disease and 2 indicates the absence of the disease.

#### Features
The dataset contains the following attributes: Age, Gender, Total Bilirubin, Direct Bilirubin, Alkaline Phosphotase, Alamine Aminotransferase, Aspartate Aminotransferase, Total Proteins, Albumin, Albumin and Globulin Ratio, and Dataset (the binary target variable).



### Project Pipeline
1. Exploratory Data Analysis (EDA):
The first step involved performing Exploratory Data Analysis. Countplots were used to analyze the distribution of the target classes and revealed that the dataset is slightly imbalanced. Histograms and boxplots were used to examine the distribution of individual features. Correlation heatmaps were applied to identify relationships and possible multicollinearity between features. Additionally, jointplots were generated to study significant relationships, such as that between Albumin and Total Proteins.

2. Feature Engineering:
During feature engineering, missing values in the "Albumin_and_Globulin_Ratio" feature were replaced with the mean of that column. The "Gender" feature was label-encoded with binary values, where Male was represented as 1 and Female as 0. Other missing values were imputed using the domain-informed constant value of 0.94. Non-informative or redundant records were dropped to improve data quality.

3. Feature Selection:
Features were selected based on correlation analysis and domain expertise. Those with higher predictive power and medical relevance were retained for model building.

4. Model Building:
The dataset was split into training and testing subsets. Multiple supervised learning classifiers were evaluated, and Logistic Regression was chosen for its simplicity, interpretability, and stable performance. For educational purposes, Logistic Regression was also implemented from scratch using gradient descent and the sigmoid function.

5. Model Evaluation:
The trained model was evaluated using metrics such as precision, recall, and F1-score for both target classes. Special emphasis was placed on achieving a high recall for the positive class (patients with liver disease) to minimize false negatives.

6. Model Serialization:
Once the model achieved satisfactory performance, it was saved as a .pkl file using the joblib library. This enabled the trained model to be reused during the deployment phase without retraining.

### Deployment Architecture: 
The application was deployed locally using Flask, a lightweight Python web framework. The frontend was developed using basic HTML and CSS. The trained model (Random Forest Classifier saved as .pkl) was loaded and used for predictions through Flask routing logic. The main application file app.py contains all Flask-based server-side code. User inputs were captured through the liver.html form, and the prediction results were rendered on result.html. The application ran on the local development server at localhost:5000.


### Sample of Application

#### Note: Focus was primarily on model logic and backend integration. Frontend kept minimal to prioritize functionality. Project serves as both a practical deployment example and a conceptual learning exercise.
