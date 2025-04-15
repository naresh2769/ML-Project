
# 📈 Bitcoin Price Prediction using ARIMA

> Author: **naresh2769**  
> Project Type: Time Series Forecasting  
> Language: Python  
> Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, `scipy`

---

## 📌 Overview

This project performs time series analysis and forecasting of Bitcoin prices using the ARIMA (AutoRegressive Integrated Moving Average) and SARIMA (Seasonal ARIMA) models. The dataset includes minute-level Bitcoin price data from **January 2012 to May 2017**, which is then resampled monthly for analysis and prediction.

---

## 📂 Dataset

- **File:** `btceUSD_1-min_data_2012-01-01_to_2017-05-31.csv.zip`
- **Columns:**
  - `Timestamp`, `Open`, `High`, `Low`, `Close`, `Volume_(BTC)`, `Volume_(Currency)`, `Weighted_Price`

---

## 📊 Workflow

### 1. **Data Preprocessing**
- Converted Unix `Timestamp` to `datetime`
- Resampled the data by day (`D`), month (`M`), quarter (`Q`), and year (`A`)
- Plotted raw time series at different resampling levels

### 2. **Stationarity Check**
- Used Dickey-Fuller test for stationarity
- Applied Box-Cox transformation to stabilize variance
- Performed seasonal and regular differentiation to achieve stationarity

### 3. **Modeling**
- Parameter tuning with grid search over `(p,d,q)x(P,D,Q,12)` using AIC for model selection
- Best SARIMA model: `SARIMAX(1,1,0)x(2,1,0,12)`
- Model evaluation with residual analysis and ACF plots

### 4. **Forecasting**
- Extended the monthly dataset with future dates up to Jan 2018
- Predicted Bitcoin prices and plotted forecast vs actuals

---

## 🧪 Results

- The Dickey-Fuller test confirmed stationarity after transformations
- The chosen model had the lowest AIC of `220.33`
- Residuals were white noise (Dickey-Fuller test p=0.000)
- Visualization showed good alignment of prediction with actual values

---

## 📌 Requirements

- Python 3.x
- Libraries:
  ```bash
  pip install pandas numpy matplotlib seaborn scipy statsmodels
  ```

---

## 📅 Time Series Model Summary

```
SARIMAX(1, 1, 0)x(2, 1, 0, 12)
AIC = 220.33
```

---

## 📉 Sample Output Plot

Shows the actual vs predicted monthly Bitcoin prices with forecast into 2018.


