# 🏡 California Housing Price Prediction

A clean end-to-end Machine Learning workflow using scikit-learn.

---

## 📌 Project Overview

This project builds a **Linear Regression** model to predict median housing values in California using the **California Housing Dataset** from scikit-learn.

It demonstrates a complete ML workflow, including:

- Data loading  
- Train-test splitting  
- Exploratory Data Analysis (EDA)  
- Data preprocessing with Pipelines  
- Model training and evaluation  
- Residual diagnostics  

🎯 **Goal**: Create a reproducible, leakage-free ML pipeline.

---

## 🛠 Technologies Used

- Python  
- NumPy  
- Pandas  
- Matplotlib  
- Scikit-learn  

---

## 📊 Dataset Description

- **Dataset**: California Housing Dataset (from `scikit-learn`)  
- **Target variable**:  
  - `MedHouseVal` (Median house value)  
- **Feature variables include**:
  - `MedInc` (Median income)  
  - `HouseAge`  
  - `AveRooms`  
  - `Population`  
  - `Latitude`  
  - `Longitude`  
  - Various socio-demographic attributes  

---

## 🔄 Workflow Summary

### 1. Load the Dataset
```python
from sklearn.datasets import fetch_california_housing
data = fetch_california_housing(as_frame=True)
df = data.frame

X = df.drop(columns=['MedHouseVal'])
y = df['MedHouseVal']

### 3. 📊 Train-Test Split

- 80% training  
- 20% testing  
- `random_state=42`

---

### 4. 🔍 Exploratory Data Analysis

**Example EDA**:  
- Histogram of Median Income (`MedInc`)  
- ⚠️ Done **only on training data** to avoid leakage

---

### 5. 🧱 Preprocessing and Modeling Pipeline

Pipeline includes:
- Median imputation  
- Standard scaling  
- Linear Regression model

---

### 6. 🏋️ Model Training

- Trained **only on the training data**

---

### 7. 🔮 Prediction

- Model predictions are generated on the **unseen test data**

---

### 8. 📏 Model Evaluation

**Metrics used:**
- Mean Absolute Error (**MAE**)  
- Root Mean Squared Error (**RMSE**)  
- R² Score

---

### 9. 📉 Residual Diagnostics

**Residual plot:**
- **X-axis**: Predicted values  
- **Y-axis**: Residuals (Actual – Predicted)  
- A horizontal zero line is drawn for visual analysis

---

### 📈 Sample Results

| Metric | Value (Approx.) |
|--------|-----------------|
| MAE    | 0.53            |
| RMSE   | 0.74            |
| R²     | 0.60            |

___

### 📁 Project Structure
├── california_housing_prediction.ipynb
├── README.md
└── requirements.txt
