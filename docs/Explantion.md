# Project Explanation: SageMaker XGBoost Model Training

## Problem Statement

The objective of this project is to build a machine learning model that predicts whether an individual's income is less than $50,000 per year. This is a binary classification problem.

---

## Approach

The project is implemented using Amazon SageMaker and follows two different approaches:

1. Built-in XGBoost Algorithm
2. Script Mode with Custom Training Code

---

## Data

- The dataset was preprocessed and stored in Amazon S3
- Split into:
  - Training set (70%)
  - Validation set (20%)
  - Test set (10%)

---

## Model 1: Built-in XGBoost

- Used SageMaker's built-in XGBoost algorithm
- Configured estimator and hyperparameters
- Trained using `.fit()` method
- Evaluated using SageMaker Debugger

### Outcome
- Quick setup and training
- Provided baseline performance

---

## Model 2: Script Mode XGBoost

- Implemented custom training script (`xgboost_train.py`)
- Enabled additional features like cross-validation
- Integrated with SageMaker Estimator

### Hyperparameter Tuning

- Used SageMaker Hyperparameter Tuning Job
- Explored multiple combinations of parameters:
  - max_depth
  - eta (learning rate)
  - gamma
  - subsample

### Outcome
- Achieved improved performance compared to built-in model
- Best objective value reached: **0.90**

---

## Model Evaluation

Model performance was evaluated using:

- Confusion Matrix
- Precision
- Recall
- F1-Score
- ROC Curve
- Feature Importance

### Key Metric: F1-Score

F1-score was chosen as the primary evaluation metric because:
- It balances precision and recall
- It considers both false positives and false negatives
- Important for this use case where misclassification has real-world impact

---

## Results Summary

| Model Type | Performance |
|-----------|------------|
| Built-in XGBoost | Baseline |
| Script Mode + Tuning | Improved (0.90 objective value) |

---

## Key Learnings

- Learned how to train models using SageMaker built-in algorithms
- Understood how to write custom training scripts
- Gained experience with hyperparameter tuning
- Learned how to evaluate models using multiple metrics
- Understood trade-offs between simplicity and flexibility

---

## Conclusion

This project demonstrates how Amazon SageMaker can be used for both quick model development and advanced machine learning workflows.

Using script mode and hyperparameter tuning significantly improved the model performance, making it more suitable for real-world applications.