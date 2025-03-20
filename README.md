# Predictive Maintenance for Turbofan Engines

## Overview
This project focuses on predicting the **Remaining Useful Life (RUL)** of turbofan engines using sensor data. The goal is to build a machine learning model that can accurately estimate how many operational cycles an engine has left before it requires maintenance or fails. This is a critical task in industries like aerospace and manufacturing, where predictive maintenance can save costs and prevent unexpected downtime.

The project uses the **NASA Turbofan Engine Degradation Simulation Dataset**, which contains sensor data from multiple engines simulated under different conditions. The dataset is available on [Kaggle](https://www.kaggle.com/datasets/behrad3d/nasa-cmaps).

---

## Project Goals
1. **Data Preprocessing**: Clean and preprocess the sensor data to make it suitable for machine learning.
2. **Feature Engineering**: Create meaningful features (e.g., rolling averages, cumulative sums) to capture trends and patterns in the data.
3. **Model Building**: Train and evaluate machine learning models (e.g., Random Forest, XGBoost, LightGBM) to predict RUL.
4. **Model Optimization**: Use hyperparameter tuning and ensemble learning to improve model performance.
5. **Visualization**: Visualize the results to understand model performance and insights.

---

## Dataset
The dataset consists of:
- **Training Data**: Sensor readings from multiple engines, each running until failure.
- **Test Data**: Sensor readings from engines, with the goal of predicting their RUL.
- **RUL Data**: The actual remaining useful life for each engine in the test set.

The dataset includes:
- **21 sensor readings** (e.g., temperature, pressure, fan speed).
- **3 operational settings** (e.g., throttle setting, altitude).
- **Time in cycles**: The number of operational cycles for each engine.

---

## Methodology
1. **Data Preprocessing**:
   - Handle missing values and normalize sensor data.
   - Calculate RUL for the training data.
   - Merge RUL with the test data.

2. **Feature Engineering**:
   - Add rolling averages and standard deviations for sensor values.
   - Create cumulative sums and interaction features.
   - Add time-based features (e.g., time since last maintenance).

3. **Model Building**:
   - Train a **Random Forest** model as a baseline.
   - Use **XGBoost** and **LightGBM** for improved performance.
   - Combine predictions using **ensemble learning**.

4. **Model Evaluation**:
   - Evaluate models using **Mean Absolute Error (MAE)** and **Root Mean Squared Error (RMSE)**.
   - Visualize actual vs. predicted RUL.

5. **Hyperparameter Tuning**:
   - Use **GridSearchCV** to find the best hyperparameters for XGBoost.

---

## Results
- **Baseline Model (Random Forest)**:
  - MAE: ~73.42
  - RMSE: ~86.46

- **Tuned XGBoost Model**:
  - MAE: ~70.54
  - RMSE: ~83.95

- **LightGBM Model**:
  - MAE: ~68.21
  - RMSE: ~81.34

- **Ensemble Model (XGBoost + LightGBM)**:
  - MAE: ~67.89
  - RMSE: ~80.12
