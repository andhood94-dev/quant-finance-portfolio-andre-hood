# Quantitative Finance Portfolio — Andre Hood

This repository showcases quantitative finance and data modeling projects I’ve worked on, including:

1. **Time-Series Forecasting**  
   ARIMA/GARCH forecasting with walk-forward validation.

2. **Multi-Factor Risk Model**  
   Estimating Fama–French and Momentum factor exposures and long/short portfolio construction.

3. **Options Pricing**  
   Black–Scholes pricing, Greeks, and Monte Carlo validation.

4. **Portfolio Optimization**  
   Mean-variance and CVaR-based portfolio construction under risk constraints.

5. **ML Alpha Signals**  
   Machine learning models using technical features to predict next-day returns.

---

## Tech Stack

- **Languages:** Python, R, SQL
- **Libraries (examples):** pandas, NumPy, SciPy, statsmodels, scikit-learn, matplotlib
- **Methods:** time-series modeling, regression, optimization, risk modeling

Each project folder contains its own README and code or notebooks showing the end-to-end workflow.

# Time-Series Forecasting

## Overview

This project demonstrates time-series forecasting of financial returns using ARIMA and GARCH models with walk-forward validation.

## Methods

- ARIMA for conditional mean modeling
- GARCH-type models for conditional volatility
- Rolling / walk-forward training and evaluation
- Evaluation metrics: RMSE / MAE, out-of-sample log-likelihood

## Files

- `src/time_series_forecasting.py` – Loads price data, computes returns, fits ARIMA/GARCH, and evaluates forecasts.

## How to Run

1. Install dependencies (example):
   ```bash
   pip install pandas numpy statsmodels arch matplotlib

   python src/time_series_forecasting.py
