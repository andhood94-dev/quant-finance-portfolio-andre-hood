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

   
---

### B. `multi-factor-risk-model/README.md`

```markdown
# Multi-Factor Risk Model

## Overview

This project builds a multi-factor risk model estimating exposures to Fama–French style factors and a Momentum factor, then uses those betas to construct and evaluate a long/short portfolio.

## Methods

- Factor construction (Market, Size, Value, Momentum, etc.)
- Time-series regression of asset returns on factors
- Estimation of factor betas and specific risk
- Long/short portfolio construction based on factor exposures

## Files

- `src/multi_factor_risk_model.py` – Constructs factors, estimates betas, and simulates a long/short portfolio with performance stats.

## How to Run

1. Install dependencies:
   ```bash
   pip install pandas numpy statsmodels matplotlib

   python src/options_pricing.py

   
---

### D. `portfolio-optimization/README.md`

```markdown
# Portfolio Optimization

## Overview

This project constructs optimized portfolios using mean-variance and CVaR (Conditional Value-at-Risk) approaches under basic constraints.

## Methods

- Estimation of expected returns and covariance matrix
- Mean-variance optimization (Markowitz)
- CVaR optimization using scenario returns
- Constraints: long-only or limited shorting, budget, max weight

## Files

- `src/portfolio_optimization.py` – Loads historical returns, sets up optimization problems, and outputs efficient portfolios.

## How to Run

1. Install dependencies:
   ```bash
   pip install pandas numpy scipy cvxpy matplotlib


---

### E. `ml-alpha-signals/README.md`

```markdown
# ML Alpha Signals

## Overview

This project builds machine learning models that use technical indicators and other features to predict next-day returns, illustrating alpha signal generation.

## Methods

- Feature engineering: returns, moving averages, RSI, volatility, etc.
- Train/test split with time-aware cross-validation
- Models: logistic regression / random forest / gradient boosting (as examples)
- Evaluation: accuracy, precision/recall, ROC-AUC, information coefficient

## Files

- `src/ml_alpha_signals.py` – Creates features, trains models, and evaluates predictive performance.

## How to Run

1. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib

   python src/ml_alpha_signals.py
