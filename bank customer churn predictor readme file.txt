# Customer Churn Prediction API

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-0.68.0-green)
![XGBoost](https://img.shields.io/badge/XGBoost-1.3.0-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

A machine learning API for predicting customer churn and recommending retention strategies in banking/financial services.

## Features

- **Predictive Modeling**: XGBoost classifier with 85%+ accuracy
- **Feature Engineering**: 15+ engineered features for better predictions
- **Hyperparameter Tuning**: Optimized with Bayesian search
- **Imbalance Handling**: SMOTE oversampling + class weighting
- **REST API**: FastAPI endpoints for predictions and recommendations
- **Actionable Insights**: Personalized retention strategies

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/customer-churn-api.git
cd customer-churn-api

Create and activate virtual environment:
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate  # Windows

Install dependencies:
pip install -r requirements.txt

Project Structure
.
├── api/                  # FastAPI application
│   ├── main.py           # Core API endpoints
│   └── schemas.py        # Pydantic models
├── notebooks/            # Jupyter notebooks
│   ├── EDA.ipynb         # Exploratory analysis
│   └── Modeling.ipynb    # Model development
├── models/               # Serialized models
│   ├── best_model.pkl    # Trained XGBoost
│   └── scaler.pkl        # Feature scaler
├── data/                 # Dataset files
│   └── churn_data.csv    # Sample dataset
├── tests/                # Unit tests
└── requirements.txt      # Dependencies

Usage
1. Train the Model
Run the training pipeline:

bash
python train.py
2. Start the API
bash
uvicorn api.main:app --reload
API will be available at http://localhost:8000

3. API Endpoints
POST /predict

Predict churn probability for a customer

Example request:

json
{
  "CreditScore": 650,
  "Age": 42,
  "Tenure": 3,
  "Balance": 125000.50,
  "NumOfProducts": 2,
  "HasCrCard": 1,
  "IsActiveMember": 1,
  "EstimatedSalary": 85000.75,
  "Geography_Germany": 1,
  "Geography_Spain": 0,
  "Gender_Male": 1
}
POST /recommend

Get personalized retention strategies

Returns:

json
{
  "churn_probability": 0.72,
  "risk_level": "high",
  "recommended_actions": [
    "Assign premium relationship manager",
    "Immediate personal call from retention team"
  ]
}
Key Features Implemented
Feature Engineering
Customer tenure segments (New/Developing/Established/Loyal)

Financial health indicators

Product engagement scores

Demographic clusters

10+ interaction features

Model Optimization
Bayesian hyperparameter tuning

Class imbalance handling (SMOTE + class weights)

Feature importance analysis

Threshold optimization (F1-maximization)

Example Notebooks
Exploratory Data Analysis

Data visualization

Correlation analysis

Feature distributions

Model Development

Feature engineering

Model training

Evaluation metrics

Deployment
Docker
bash
docker build -t churn-api .
docker run -p 8000:8000 churn-api
AWS Elastic Beanstalk
bash
eb init -p python-3.8 churn-api
eb create churn-api-env
Contributors