# ✈️ Flight Price Prediction using AWS SageMaker & Streamlit

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![AWS SageMaker](https://img.shields.io/badge/AWS-SageMaker-orange.svg)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-green.svg)
![Streamlit](https://img.shields.io/badge/UI-Streamlit-red.svg)

---

## 🛫 Project Overview

This project implements an **end-to-end Flight Price Prediction system** using **AWS SageMaker** for scalable model training and hyperparameter tuning, and **Streamlit** for an interactive, user-friendly web interface.

The system predicts flight ticket prices based on airline, journey date, route, duration, stops, and timing features using an advanced **XGBoost regression model**.

---

## 🎯 Key Objectives

- Predict flight prices accurately using machine learning
- Apply advanced feature engineering techniques
- Train and tune models using AWS SageMaker
- Ensure consistent preprocessing between training and inference
- Provide an intuitive UI for real-time predictions

---

## 🧠 Machine Learning Pipeline

### ✔ Feature Engineering
- Date feature extraction (month, week, day)
- Time-of-day categorization
- Route-based geographic flags
- Duration transformations (RBF similarity, bins)
- Rare category handling
- Encoding using Mean, Frequency & One-Hot encoders
- Feature selection using RandomForest performance

### ✔ Model Training
- Algorithm: **XGBoost Regressor**
- Objective: `reg:squarederror`
- Hyperparameter tuning via **SageMaker HyperparameterTuner**
- Metric optimized: **Validation RMSE**

### ✔ Model Inference
- Saved preprocessing pipeline (`preprocessor.joblib`)
- Saved trained model (`xgboost-model`)
- Consistent transformations for predictions

---

## ☁️ AWS SageMaker Usage

- Spot instances for cost-efficient training
- Bayesian hyperparameter optimization
- Model artifacts stored on Amazon S3
- Training executed in managed SageMaker containers

---

## 🖥 Streamlit Web Application

The Streamlit UI allows users to:

- Select airline, source, destination
- Choose journey date, departure & arrival times
- Enter flight duration and number of stops
- View:
  - 📈 Predicted price
  - 📉 Confidence interval
  - 📊 Historical price distribution

---

## 📁 Repository Structure

```
📦 Sagemaker-Flight-Prediction
├── data/
│ └── train.csv
│
├── notebooks/
│ ├── feature-engineering.ipynb
│ └── model-training.ipynb
│
├── app.py
├── preprocessor.joblib
├── xgboost-model
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/MuktiKsinha/Sagemaker-Flight-Prediction.git
cd Sagemaker-Flight-Prediction


python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows

pip install -r requirements.txt

streamlit run app.py

http://localhost:8501
```

📊 Price Distribution Visualization

The app includes a histogram showing the distribution of historical flight prices, helping users understand pricing behavior.

X-axis: Ticket Price (INR)

Y-axis: Number of Flights

🚢 Deployment Options

Streamlit Community Cloud

AWS App Runner

Docker + AWS ECS

EC2 with Nginx & Gunicorn
