# Quantitative Finance Portfolio — Andre Hood

Each of my projects demonstrates mastery in core area Citadel values:
   Statistical modeling,
   Machine learning for prediction,
   Market microstructure & volatility understanding,
   Factor risk modeling,
   Portfolio construction under constraints,
   Simulation and derivative pricing, and
   Data-driven decision making.

Together, they display my ability to build, test, and refine systematic models — the foundation of high-performance quantitative work at Citadel.

1. **Time-Series Forecasting for Financial Returns — Personal Quant Project**  
    Built ARIMA and GARCH-based models in Python to forecast daily equity returns and volatility using
    walk-forward validation.

2. ****  
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

   
---

## 4. (Optional) Python file skeletons

Here’s a minimal skeleton you can paste into, say, `src/time_series_forecasting.py` and then fill in:

```python
import pandas as pd
import numpy as np
from statsmodels.tsa.arima.model import ARIMA
from arch import arch_model
import matplotlib.pyplot as plt

def load_data(path: str) -> pd.Series:
    """Load price data and return log returns."""
    prices = pd.read_csv(path, parse_dates=["date"], index_col="date")["price"]
    returns = np.log(prices).diff().dropna()
    return returns

def fit_arima(returns: pd.Series):
    model = ARIMA(returns, order=(1, 0, 1))
    return model.fit()

def fit_garch(returns: pd.Series):
    model = arch_model(returns * 100, vol="Garch", p=1, q=1, dist="normal")
    return model.fit(disp="off")

def main():
    returns = load_data("data/prices.csv")
    arima_res = fit_arima(returns)
    garch_res = fit_garch(returns)
    print(arima_res.summary())
    print(garch_res.summary())

if __name__ == "__main__":
    main()
