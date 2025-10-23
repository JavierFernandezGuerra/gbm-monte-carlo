# 📈 Price Trajectory Simulation with Geometric Brownian Motion

**Author:** Javier Fernández Guerra

## Overview

This project models the **price evolution of a financial asset** (S&P 500) using a **Geometric Brownian Motion (GBM)** stochastic process. It includes Monte Carlo simulations, statistical analysis, and risk visualization.

> You can find the **English version** of the notebook as `GBM_ENG_Javier_Fernández_Guerra.ipynb`.  
> A **Spanish version** is also available as `GBM_ESP_Javier_Fernández_Guerra.ipynb`.


## Features

* Historical data download via `yfinance`
* Drift (μ) and volatility (σ) estimation
* Exact analytical GBM simulation
* Descriptive statistics (mean, variance, skewness, kurtosis)
* Risk metrics: Value at Risk (VaR), Conditional VaR (CVaR), Maximum Drawdown
* Visualizations: simulated trajectories, final price distribution, and drawdown histogram

## Workflow

1. Download S&P 500 historical data
2. Compute logarithmic returns
3. Estimate drift (μ) and volatility (σ)
4. Simulate price paths using the GBM formula:

   ```python
   S(t+Δt) = S(t) * exp((μ - 0.5σ²)Δt + σ√Δt * Z)
   ```
5. Analyze descriptive statistics and risk measures
6. Visualize results

## Requirements

```bash
pip install numpy pandas matplotlib scipy yfinance
```

## Key Parameters

| Parameter        | Description                | Example      |
| ---------------- | -------------------------- | ------------ |
| `ticker`         | Asset symbol               | `^GSPC`      |
| `start_date`     | Historical data start date | `2020-03-23` |
| `T_trading_days` | Trading days horizon       | 252          |
| `dt`             | Time step                  | 0.05         |
| `n_trajectories` | Monte Carlo paths          | 1000         |
| `alpha`          | VaR/CVaR confidence level  | 0.01         |
| `seed`           | Random seed                | 42           |

## Outputs

* **Simulated Trajectories:** 1000 Monte Carlo paths with the average highlighted.
* **Final Price Distribution:** Comparison with normal fit and risk thresholds (VaR, CVaR).
* **Max Drawdown Distribution:** Histogram with mean, median, and 99th percentile markers.

## References

* Wilmott, P. (2006). *Paul Wilmott on Quantitative Finance*. John Wiley & Sons.
* McKinney, W. (2017). *Python for Data Analysis*. O’Reilly Media.

## Usage

```bash
git clone https://github.com/<your-username>/GBM_ENG_Javier_Fernández_Guerra.git
cd GBM_ENG_Javier_Fernández_Guerra
jupyter notebook GBM_ENG_Javier_Fernández_Guerra.ipynb
```

Run all cells to reproduce simulations and plots.

> Quantitative exploration of stochastic price dynamics using Python and Monte Carlo methods.
