# Training ML Model: Built-in vs Script Mode in Amazon SageMaker

A comprehensive comparison of training XGBoost models using Amazon SageMaker's built-in algorithm vs. script mode, demonstrating different approaches to machine learning model development and deployment.

## 🏗️ Architecture Overview

![Architecture Diagram](./Architecture/Architecture%20diagram.png)

The project architecture consists of:
- **Data Storage**: Preprocessed datasets stored in Amazon S3
- **Training Environments**: Two SageMaker training jobs (Built-in vs Script Mode)
- **Model Evaluation**: Comprehensive metrics and visualizations
- **Hyperparameter Tuning**: Automated optimization for script mode

## 📋 Table of Contents

- [Problem Statement](#-problem-statement)
- [Approach](#-approach)
- [Project Structure](#-project-structure)
- [Installation & Setup](#-installation--setup)
- [Usage](#-usage)
- [Results](#-results)
- [Key Learnings](#-key-learnings)
- [Contributing](#-contributing)
- [License](#-license)

## 🎯 Problem Statement

Build a machine learning model to predict whether an individual's annual income exceeds $50,000 based on demographic and employment data. This binary classification problem uses the Adult Census Income dataset.

## 🔄 Approach

The project implements two distinct training methodologies in Amazon SageMaker:

### 1. Built-in XGBoost Algorithm
- Utilizes SageMaker's pre-configured XGBoost container
- Minimal setup with high-level API calls
- Focuses on rapid prototyping and baseline performance

### 2. Script Mode with Custom Training
- Custom training script with full control over the training process
- Implements advanced techniques like cross-validation
- Integrated hyperparameter tuning for optimization

## 📁 Project Structure

```
Traning_ML_Model_1builtin_2scriptmode/
├── Architecture/
│   └── Architecture diagram.png          # System architecture visualization
├── data/
│   ├── Train/                            # Training datasets
│   ├── Test/                             # Test datasets
│   └── Validate/                         # Validation datasets
├── docs/
│   ├── Built-in vs Script Mode in Amazon SageMaker.md
│   └── Explantion.md                     # Detailed project explanation
├── notebooks/
│   ├── train_built_in.ipynb              # Built-in algorithm notebook
│   ├── train_script_mode.ipynb           # Script mode notebook
│   └── xgboost_report (1).ipynb          # Model evaluation and reporting
├── screenshots/                          # Training and evaluation screenshots
├── src/
│   └── xgboost_train.py                  # Custom training script
├── xgboost_reports_json/                 # Model evaluation metrics (JSON)
│   ├── ConfusionMatrix.json
│   ├── EvaluationMetrics.json
│   ├── FeatureImportance.json
│   ├── IterativeClassAccuracy.json
│   ├── LabelsDistribution.json
│   ├── LossData.json
│   ├── ResidualDistribution.json
│   └── ROCCurve.json
└── README.md
```

## 🚀 Installation & Setup

### Prerequisites
- AWS Account with SageMaker access
- Python 3.7+
- AWS CLI configured
- SageMaker SDK

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/VinuthnaReddy07/Traning_ML_Model_1builtin_2scriptmode.git
   cd Traning_ML_Model_1builtin_2scriptmode
   ```

2. **Install dependencies**
   ```bash
   pip install boto3 sagemaker scikit-learn pandas numpy matplotlib seaborn
   ```

3. **Configure AWS**
   ```bash
   aws configure
   ```

4. **Upload data to S3**
   - Create an S3 bucket
   - Upload the datasets from `data/` folder

## 📖 Usage

### Built-in Algorithm Approach
Run the `notebooks/train_built_in.ipynb` notebook to:
- Set up SageMaker estimator
- Configure hyperparameters
- Train using built-in XGBoost
- Evaluate model performance

### Script Mode Approach
Run the `notebooks/train_script_mode.ipynb` notebook to:
- Execute custom training script
- Perform hyperparameter tuning
- Implement cross-validation
- Generate detailed evaluation reports

### Model Evaluation
Use `notebooks/xgboost_report (1).ipynb` to:
- Visualize confusion matrices
- Plot ROC curves
- Analyze feature importance
- Compare model performance

## 📊 Results

### Performance Comparison

| Model Type | Ease of Use | Flexibility | Performance | Best Objective |
|-----------|-------------|-------------|-------------|---------------|
| Built-in XGBoost | ⭐⭐⭐⭐⭐ | ⭐⭐ | Baseline | - |
| Script Mode + Tuning | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Improved | **0.90** |

### Key Metrics
- **Primary Metric**: F1-Score (balances precision and recall)
- **Evaluation**: Confusion Matrix, ROC Curve, Feature Importance
- **Hyperparameter Tuning**: max_depth, eta, gamma, subsample

## 🎓 Key Learnings

- **SageMaker Built-in Algorithms**: Quick setup for baseline models
- **Script Mode**: Full control over training logic and evaluation
- **Hyperparameter Tuning**: Systematic optimization of model parameters
- **Model Evaluation**: Comprehensive metrics for real-world deployment
- **Trade-offs**: Simplicity vs. flexibility in ML workflows

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.



**Note**: This project demonstrates machine learning best practices using AWS SageMaker and serves as a reference for implementing both built-in and custom training approaches.