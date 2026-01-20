# Prophet-Model---Time-Series-Sales--Forecasting
Sales forecasting using time-series modeling with 6-month rolling validation
# 📊 Sales Forecasting Using Time-Series Modeling

## 🔍 Project Overview
This project focuses on building a **robust and business-ready time-series forecasting model** to predict **monthly product unit sales**.  
The model is designed to meet strict accuracy requirements using **rolling 6-month unseen validation** and **Mean Absolute Percentage Error (MAPE)** as the evaluation metric

The solution uses **Facebook Prophet** enhanced with **external regressors**, **custom seasonality**, and **leakage-free validation**, ensuring both academic rigor and real-world applicability.

---

## 🎯 Objectives
The primary objectives of this project are:

- Predict monthly **product unit sales**
- Ensure **Month-on-Month (MoM) MAPE ≤ 15%**
- Ensure **Overall 6-Month MAPE ≤ 15%**
- Prevent data leakage using rolling validation
- Capture real-world effects using external factors

---

## 📁 Dataset Description
The dataset contains daily sales information and is aggregated to a monthly level.

### Columns Used
| Column | Description |
|------|-------------|
| sale_date | Date of sale |
| product_unit_sales | Target variable |
| discount_amount (Rs.) | Promotional impact |
| mrp_amount (Rs.) | Price influence |
| product | Product category |

Only a **single product** is modeled to avoid mixing different sales behaviors.

---

## 🔄 Methodology

### 1️⃣ Data Preparation
- Converted date column to datetime
- Sorted chronologically
- Aggregated daily data → **monthly time series**
- Applied **log transformation** to stabilize variance

---

### 2️⃣ Exploratory Data Analysis
- Trend visualization to detect growth or decline
- Seasonal analysis to identify recurring monthly patterns

---

### 3️⃣ Model Selection
**Facebook Prophet** was chosen due to:
- Built-in handling of trend and seasonality
- Support for external regressors
- Robust performance on business time-series data

---

### 4️⃣ External Regressors
To capture real-world sales drivers:
- Discount amount
- MRP (price)

These improve forecasting accuracy and realism.

---

### 5️⃣ Rolling 6-Month Validation (Key Requirement)
A rolling-window approach was used:
- Training data grows with time
- Validation set always consists of the **next 6 unseen months**
- Repeated across the dataset

This ensures **zero data leakage**.

---

### 6️⃣ Evaluation Metrics
Two accuracy checks were performed:

- **Month-on-Month MAPE**  
- **Overall 6-Month Cumulative MAPE**

Both were required to stay within **15% error**.

A **naive baseline model** was also implemented for comparison.

---

## 📈 Results Summary
- Prophet consistently outperformed the naive baseline
- Majority of rolling validation windows met the ≤ 15% error threshold
- Model demonstrated stability across multiple time periods

---

## 🔮 Final Forecast
- Trained on full historical data
- Generated **next 6-month sales forecast**
- Included uncertainty bounds

---

## 🛠️ Tools & Technologies
- Python
- Pandas, NumPy
- Facebook Prophet
- Scikit-learn
- Matplotlib
- Google Colab

---

## 📌 Key Takeaways
- Rolling validation prevents overly optimistic results
- External regressors significantly improve accuracy
- Prophet provides an interpretable and scalable forecasting solution

---

## 👤 Author
**Rohan Rg**  
M.Tech CSE (AI & ML)

---

## 📂 Repository Structure
