# Stroke Prediction



## Overview

Stroke has been one of the leading causes of death around the world for decades. Tools that can help detect stroke risks in patients could prove useful in saving many lives all around the world.

According to several reports cited by the CDC:

* Every 40 seconds, somebody in the United States has a stroke. <sup>1</sup>
* About 360 people die from strokes everyday in the United States.<sup>1</sup>
* Stroke-related costs in the United States came to nearly $46 billion between 2014 and 2015.<sup>1</sup>
* Stroke is a leading cause of serious long-term disability. Stroke reduces mobility in more than half of stroke survivors age 65 and over.<sup>1</sup>

**Project Goal:**

Based on a set of information about a patient's health, predict whether that patient is likely to experience a stroke in the near future.

## Data

link to dataset: https://www.kaggle.com/fedesoriano/stroke-prediction-dataset

* Imbalanced
* 5110 data points total
* Split 50/50 (training/test set)



## Results

**Classification Models**

| Model               | f1-score (weighted avg) | f1-score (macro avg) |
| ------------------- | ----------------------- | -------------------- |
| Logistic Regression | 0.93                    | 0.5                  |
| Random Forest       | 0.93                    | 0.5                  |
| XGBoost             | 0.92                    | 0.51                 |
| AdaBoost            | 0.92                    | 0.51                 |
| Tree Ensemble       | 0.92                    | 0.52                 |

**Regression Models (with a classification threshold)**

| Model                     | f1-score (weighted avg) | f1-score (macro avg) |
| ------------------------- | ----------------------- | -------------------- |
| Linear Regression         | 0.86                    | 0.58                 |
| Ridge Regression          | 0.79                    | 0.52                 |
| Lasso Regression          | 0.79                    | 0.51                 |
| ElasticNet Regression     | 0.79                    | 0.51                 |
| Random Forest             | 0.93                    | 0.5                  |
| XGBoost                   | 0.81                    | 0.53                 |
| AdaBoost                  | 0.82                    | 0.54                 |
| Support Vector Regression | 0.83                    | 0.53                 |

## Models Used

With the regression models, a threshold was decided on to determine whether the prediction was positive or negative. The thresholds were decided based on the distribution of predictions and there was very little attempt to "optimise" from there forward as that would result in target leakage. Each regression model has a different threshold as they output different prediction distributions.

* Support Vector Regression
* Logistic Regression (with L2 regularisation)
* Linear Regression
  * Simple
  * Ridge
  * Lasso
  * ElasticNet
* Tree Models (both regression and classification trees were tested)
  * Random Forest
  * XGBoost
  * AdaBoost



## Techniques Used

* Grid Search
* Data imputation
* A Fair Amount of Feature Engineering
* Feature Selection of Engineered Features(using Random Forest Feature Importance)



## Potential Improvements

* Upsampling
* More Advanced Imputation(eg. MICE)
* Stratified K-Fold Ensemble Model
* Focal Loss instead of BCELoss
* Try a Neural Network
* Ensemble our models (averaging or voting structure)



##### References

1. https://www.cdc.gov/stroke/facts.htm
