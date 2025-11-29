# 🚲 Bike Sharing Demand Prediction — Linear Regression

This project analyzes hourly bike rental demand using the **Bike Sharing Dataset (2011–2012)**.  
It explores temporal patterns, weather influence, and environmental factors affecting bike usage, followed by building and evaluating a **Linear Regression** model as a baseline predictor.

---

## 📌 Project Overview
The goal of this project is to:

- Understand how weather, season, time, and user behavior influence hourly bike demand  
- Perform detailed EDA (temporal, seasonal, weather-based trends)  
- Build a baseline **Linear Regression** model  
- Interpret coefficients and feature importance  
- Identify model strengths, weaknesses, and improvement paths  

The regression model achieved:
- **R² Score:** 0.396  
- **MAE:** 104.08  
- **RMSE:** 138.80  

Although linear regression provides interpretability and transparency, the dataset exhibits complex nonlinear patterns that require advanced models.

---

## 📁 Dataset Details

The dataset contains **hourly bike rental records** from a bike-sharing system, with 17 features including:

- **Time-related:** season, year, month, hour, weekday, workingday  
- **Weather-related:** temperature (temp), feeling temperature (atemp), humidity (hum), windspeed  
- **User counts:** casual, registered  
- **Target variable:** `cnt` (total bike rentals per hour)

No missing values were found, and preprocessing included datetime merging, label mapping, and removal of redundant fields.

---

## 🔍 Exploratory Data Analysis (Summary)

### **1. Temporal Patterns**
- Clear **bimodal peaks** at **8 AM** and **5–6 PM**, aligning with commuting times  
- Weekends/holidays show flatter demand curves, indicating recreational use  

### **2. Seasonal Behaviour**
- **Spring has lowest demand**  
- **Summer, Fall, Winter** show similar higher demand levels  

### **3. Weather Effects**
- Clear & Misty conditions → highest usage  
- Light rain/snow → moderate drop  
- Heavy rain/snow → very low usage  

### **4. Correlation Insights**
- `temp` and `atemp` are highly correlated (0.99)  
- Humidity negatively impacts demand  
- Registered users strongly influence total demand  

---

## 🧠 Model Summary

### **Model Used**
- Baseline **Multiple Linear Regression**  
- Predictors include hour, year, holiday, weekday, workingday, weather condition, temperature, humidity, windspeed, and season.

### **Findings**
- **Hour** is the strongest predictor (commute-linked behavior)  
- **Temperature** increases demand  
- **Humidity** suppresses ridership  
- Windspeed has negligible impact  

### **Limitations**
- Linear model underfits during peak hours  
- Produces negative predictions under low usage  
- Residuals show non-linearity and heteroscedasticity  

Advanced models (Random Forest, Gradient Boosting, XGBoost) would significantly improve accuracy.

---

## 🎯 Key Insights

- Bike demand is driven heavily by **commuting time** and **favorable weather**  
- **Humidity and bad weather drastically reduce ridership**  
- Demand patterns differ across working days and weekends  
- Baseline linear regression explains ~40% of variability — good start but insufficient for real deployment  

---

## 📦 Results Summary

| Metric | Value |
|--------|--------|
| Model | Linear Regression |
| MAE | 104.08 |
| RMSE | 138.80 |
| R² | 0.396 |
| Strongest Predictor | Hour |
| Weak Predictors | Windspeed |
| Problem Level | Moderate Nonlinearity |

---

## 🧱 Tech Stack

- Python  
- NumPy, Pandas  
- Matplotlib, Seaborn  
- Scikit-learn  
- Jupyter / Google Colab  

---

## 📂 Repository Structure
Bike-Demand-Prediction/
│
├── notebooks/
│ └── Bike_Sharing_Demand_Prediction.ipynb
├── report/
│ └── Bike Sharing Demand Prediction_Linear Regression Report.pdf
├── README.md
├── requirements.txt
└── LICENSE
