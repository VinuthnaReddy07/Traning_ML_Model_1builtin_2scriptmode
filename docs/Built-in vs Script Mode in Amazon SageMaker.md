# Built-in vs Script Mode in Amazon SageMaker

## Overview

In Amazon SageMaker, machine learning models can be trained using two different approaches:

1. Built-in Algorithm Mode  
2. Script Mode (Framework Mode)

This project implements both approaches using XGBoost and compares their flexibility, control, and performance.

---

## 1. Built-in Algorithm Mode

### Description
Built-in mode uses pre-configured algorithms provided by SageMaker. In this project, we used the built-in XGBoost container.

### Key Characteristics
- Minimal setup required
- No need to write training logic
- SageMaker handles training internally
- Limited customization

### Advantages
- Fast and easy to use
- Ideal for quick experimentation
- Requires less coding effort

### Limitations
- No control over training logic
- Cannot implement custom techniques like cross-validation
- Limited flexibility

---

## 2. Script Mode (Framework Mode)

### Description
Script mode allows you to run your own training script using frameworks like XGBoost. In this project, a custom script (`xgboost_train.py`) was used.

### Key Characteristics
- Full control over training process
- Custom data handling and preprocessing
- Ability to implement advanced techniques

### Advantages
- Supports cross-validation
- Custom evaluation metrics
- More flexible and production-ready
- Can integrate complex ML workflows

### Limitations
- Requires more coding
- Slightly more complex setup

---

## Key Differences

| Feature | Built-in Mode | Script Mode |
|--------|--------------|------------|
| Ease of Use | Easy | Moderate |
| Custom Logic | No | Yes |
| Cross-validation | No | Yes |
| Flexibility | Low | High |
| Control | Limited | Full |
| Use Case | Quick experiments | Advanced ML workflows |

---

## Conclusion

Both approaches are useful depending on the use case:

- Built-in mode is ideal for quick model development and testing.
- Script mode is preferred for real-world applications where flexibility and customization are required.

In this project, script mode combined with hyperparameter tuning resulted in better performance compared to the built-in approach.