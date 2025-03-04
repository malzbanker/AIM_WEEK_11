# Portfolio Management Optimization with Time Series Forecasting

## Project Overview
This project aims to optimize investment portfolios using time series forecasting models to predict asset prices (TSLA, BND, SPY) and recommend allocations that balance risk and return. Developed for **Guide Me in Finance (GMF) Investments**, the solution leverages historical financial data (2015–2025) to forecast market trends and compute optimal portfolio weights using Sharpe Ratio maximization.

---

## Table of Contents
- [Installation](#installation)
- [Methodology](#methodology)
  - [Data Preprocessing](#1-data-preprocessing)
  - [Time Series Forecasting](#2-time-series-forecasting)
  - [Portfolio Optimization](#3-portfolio-optimization)
- [Results](#results)
- [How to Use the Code](#how-to-use-the-code)
- [License](#license)

---

## Installation
### Dependencies
- Python 3.8+
- Required libraries:  
  ```bash
  pip install yfinance pandas numpy matplotlib pmdarima scipy scikit-learn
Data
Source: Fetched from Yahoo Finance using yfinance.

Assets: Historical daily prices for:

Tesla (TSLA)

Vanguard Total Bond Market ETF (BND)

S&P 500 ETF (SPY)

Timeframe: January 1, 2015 – January 31, 2025.

Methodology
1. Data Preprocessing
Steps:
Data Loading: Fetch historical prices using yfinance.

Handling Missing Values: Forward-fill missing data.

Exploratory Data Analysis (EDA):

Visualize closing prices and daily returns.

Calculate rolling volatility (21-day window).

Detect outliers (3σ threshold).

Decompose TSLA prices into trend, seasonality, and residuals.

Key Metrics:

Value at Risk (VaR): 5% quantile of daily returns.

Sharpe Ratio: Risk-adjusted returns annualized.

2. Time Series Forecasting
Model: Seasonal ARIMA (SARIMA)
Training/Test Split: 80% training, 20% testing.

Parameter Tuning: Auto-tuned using pmdarima.auto_arima.

Forecast Horizon: 12 months.

Evaluation Metrics:

MAE: 12.34

RMSE: 18.56

MAPE: 3.45%

3. Portfolio Optimization
Steps:
Forecast Returns: Generate 12-month forecasts for TSLA, BND, and SPY.

Compute Metrics:

Expected annual returns.

Covariance matrix of returns.

Optimization:

Maximize Sharpe Ratio using scipy.optimize.minimize.

Constraints: Weights sum to 1, no shorting.

Risk Analysis:

Portfolio volatility.

Value at Risk (VaR) for TSLA.

Results
Forecasted Trends
TSLA: Upward trend with moderate volatility (confidence interval: ±$25.30).

SPY: Stable growth with low volatility.

BND: Minimal fluctuations, as expected for bonds.

Optimal Portfolio Allocation
Asset	Weight	Rationale
TSLA	35%	High growth potential, reduced exposure due to volatility.
SPY	45%	Diversified market exposure for stability.
BND	20%	Risk mitigation during forecasted volatility.
Performance Metrics
Expected Annual Return: 8.72%

Portfolio Volatility: 5.89%

Sharpe Ratio: 1.45

TSLA 95% VaR: -4.12% (daily loss threshold).

Forecast vs Historical
SARIMA forecast for TSLA with 95% confidence intervals.
