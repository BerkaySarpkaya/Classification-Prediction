## Classification-Prediction
It is a binary classification modelling project predicting whether flight passengers were satisfied or not with their flights. The data is from Kaggle.

## Table of Contents

<!--ts-->
* [Aims and Objectives](#Aims-and-Objectives)
* [Requirements](#Requirements)
* [Dataset](#Dataset)
* [Data Preparation](#Data-Preparation)
* [Feature Engineering and Data Visualisation](#Feature-Engineering-and-Data-Visualisation)
* [Model Selection and Training](#Model-Selection-and-Training)
* [Evaluation](#Evaluation)
* [Further Work and Improvements](#Further-Work-and-Improvements)
<!--te-->

## Aims and Objectives

The main aim of this case was to build a model that could accurately predict whether passengers were satisfied with their flight or not.

The other side aims were:

- Comparison of the performance of multiple data sets scaled in different ways including: Raw, Normalization, Standardization and Robust Scaling
- Comparison of different user-ready scikit-learn models and an ANN model created with Tensorflow-Keras

## Requirements

- Python Version: 3.10.12
- Pandas Version: 1.5.3
- Numpy Version: 1.23.5
- Matplotlib Version: 3.7.1
- Seaborn Version: 0.12.2
- Tensorflow Version: 2.14.0
- Scikit-Learn Version: 1.2.2
- XGBoost Version: 2.0.0
- LightGBM Version: 4.0.0
- Catboost Version: 1.2.2

## Dataset

The data was downloaded directly from Kaggle (<a href="https://www.kaggle.com/datasets/johndddddd/customer-satisfaction/data"> Passenger Satisfaction</a>.) It is stated that the origin of the data comes from US Airline passenger satisfaction survey

## Data Preparation

- Data was in xlsx format, with ease to read.
- Imputation of missing values were conducted according to features relations
- After handling missing values, a basic reference model was prepared in order to compare the results with the final model

## Feature Engineering and Scaling

- PCA analysis and dimensionality reduction held to overcome multicollinearity problem.
- One feature, did_flight_delay, was generated from the data. The generated feature did not cause any multicollinearity problems.
- 3 different scaling method were applied to the data (Min-Max Scaling, Z-Score Scaling, Robust Scaling).

 ## Model Selection and Training

- Accuracy Score was choosen as the main metric because the target variable has balanced output values
- A range of user-ready models were selected including logistic regression, KNN, Perceptron, SVC, Bagging and Boosting Decision Tree algorithms. 
- On top of that, a basic ANN architecture was modeled with kernel-regularizer(l2=0.01). Linear activation at the and node and (from_logits=True) argument with loss function were also used to prevent computational errors by treating the output as a raw unbounded score rather than probability.
- "Different model X different scaling method" combinations were performed to see the best Accuracy Score.

Among all the different cases, the normalized and dimensionality reduction applied dataset with catboost algorithm had the best accuracy of 0.964 with the following confusion matrix

<img src="https://github.com/BerkaySarpkaya/Classification-Prediction/blob/main/Images/Confusion-Matrix-DR-Normalized-Catboost.PNG" alt="Figure 1">

<em>Figure 1. Confusion matrix of the catboost model - 96.4% accuracy</em>
