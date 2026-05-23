# Rock-and-Mine-Prediction-Logistic-Regression-
Project Overview:
This project uses a Machine Learning classification model to predict whether an object detected by sonar signals is a Rock (R) or a Mine (M). The model is trained using the Sonar dataset and implemented in Python using Scikit-learn.

The notebook performs the complete machine learning workflow including:

Data loading and preprocessing
Exploratory data analysis
Train-test splitting
Logistic Regression model training
Model evaluation
Prediction system for new input data
Dataset Information

The dataset used in this project is the Sonar Dataset.

Dataset Characteristics
Total Observations: 208
Total Features: 60 numerical attributes
Target Variable:
R → Rock
M → Mine

Each feature represents the energy of sonar signals bounced back from different surfaces.

Technologies and Libraries Used

The following Python libraries are used in this project:

import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score
Tools
Python
Jupyter Notebook
Scikit-learn
NumPy
Pandas

Project Workflow
1. Importing Libraries

Essential Python libraries are imported for data handling, model building, and evaluation.

2. Loading the Dataset

The dataset is loaded into a Pandas DataFrame.

sonar_data = pd.read_csv('Copy of sonar data.csv', header=None)
3. Data Exploration

Basic exploratory analysis is performed using:

head()
shape
info()
describe()
Missing value checking
Duplicate value checking
4. Data Preparation

The dataset is divided into:

Features (X)
Target labels (Y)
X = sonar_data.drop(columns=60, axis=1)
Y = sonar_data[60]
5. Splitting Training and Testing Data

The dataset is split into:

80% Training Data
20% Testing Data
X_train, X_test, Y_train, Y_test = train_test_split(
    X, Y, test_size=0.2, stratify=Y, random_state=1
)
Model Training

A Logistic Regression model is used for classification.

model = LogisticRegression()
model.fit(X_train, Y_train)
Model Evaluation

The model performance is evaluated using accuracy scores.

Training Accuracy
training_data_accuracy = accuracy_score(X_train_prediction, Y_train)
Testing Accuracy
test_data_accuracy = accuracy_score(X_test_prediction, Y_test)

The evaluation helps determine how well the model generalizes to unseen data.

Predictive System

The notebook also includes a predictive system where new sonar signal values can be provided as input to classify whether the object is a rock or a mine.

Example:

input_data = (...)
prediction = model.predict(input_data_reshaped)

The output will indicate:

Rock
Mine
How to Run the Project
Step 1: Install Required Libraries
pip install numpy pandas scikit-learn

Step 2: Open the Notebook
Open the Jupyter Notebook:
jupyter notebook

Step 3: Run the Notebook
Execute all cells sequentially.

Conclusion

This project demonstrates a simple and effective machine learning approach for sonar signal classification using Logistic Regression. The workflow covers the complete pipeline from data preprocessing to prediction generation, making it a useful beginner-level machine learning project.
