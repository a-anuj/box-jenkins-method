# Box–Jenkins Time Series Analysis on Apple Stock (AAPL)

This project applies the **Box–Jenkins methodology** to analyze Apple (AAPL) stock time-series data using ARIMA.  
It includes data collection, stationarity tests, differencing, ACF/PACF diagnostics, model selection using AIC/BIC, and residual validation using the Ljung–Box test.


## 1. Overview

The goal is to model Apple’s daily stock returns (2015–2023) using a statistically valid ARIMA model.  
The workflow follows the Box–Jenkins steps:

1. Identification  
2. Estimation  
3. Diagnostic checking  
4. Forecasting


## 2. Methodology (Box–Jenkins Steps)

### Step 1 — Identification
- Download AAPL prices from yfinance.  
- Convert closing prices to **log returns**.  
- Check stationarity using **ADF test**.  
- Apply **differencing** to achieve stationarity if required.  
- Plot **ACF** and **PACF** to infer AR (p) and MA (q) structure.

### Step 2 — Estimation
Fit multiple ARIMA(p, d, q) models and compute:

- Akaike Information Criterion (AIC)  
- Bayesian Information Criterion (BIC)

The best model is the one with the lowest AIC/BIC.

### Step 3 — Diagnostic Checking
Validate the fitted model by checking that residuals are white noise:

- ADF test on residuals  
- Ljung–Box autocorrelation test  
- Residual plots

### Step 4 — Interpretation
Plot observed vs. fitted values to visually inspect model performance.



## Results Summary
- Log returns were strongly stationary (ADF p-value ≈ 0).
- Best model chosen using AIC/BIC: ARIMA(0, 0, 1)
- Residuals passed ADF and Ljung–Box tests → model is statistically valid
