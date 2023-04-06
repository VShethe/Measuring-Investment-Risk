
# Measuring Investment Risk





## Table of Content


1. Measuring Investment Risk - TATAMOTORS, ICICIBANK

2. Measuring Investment Risk - WMT, META

## Project Description

1. **Covariance & Covariance:**
Covariance measures the degree to which two variables move together, while correlation measures the strength and direction of their relationship. A Covariance& Correlation matrix is useful to understand the overall risk of the portfolio and identify any strong positive or negative relationships between assets.

```bash
Formula for Covariance matrix:
cov_matrix = sec_returns.cov()

Formula for Correlation matrix:
corr_matrix = sec_returns.corr()

```
![image](https://user-images.githubusercontent.com/128286364/230365343-71bec0b5-5fcd-43c5-a9a8-312c1e609238.png)


2. **Portfolio Volatility:**
Volatility is a measure of how much an asset or portfolio's returns fluctuate over time. Portfolio volatility is calculated by taking the standard deviation of the portfolio's returns. Higher volatility implies higher risk.

```bash
Formula for Portfolio Variance:
portfolio_var = np.dot(weights.T, np.dot(sec_returns.cov(),weights))

Formula for Portfolio Volatility:
portfolio_vol = np.dot(weights.T, np.dot(sec_returns.cov(),weights))**0.5

```
3. **Diversifiable and Non-Diversifiable Risk:**
 Diversifiable risk is the risk that can be eliminated through diversification, i.e., by adding more assets to a portfolio. Non-diversifiable risk, also known as systematic risk, is the risk that is inherent in the market and cannot be eliminated through diversification.

 ```bash
Formula for Diversifiable Risk:
dr = portfolio_var - (weights[0]**2 * stock_1_var) - (weights[1]**2 * stock_2_var)

Formula for Portfolio Volatility:
n_dr = (weights[0]**2 * stock_1_var) + (weights[1]**2 * stock_2_var)

```
## Installation

To install iexfinance:

url: <https://pypi.org/project/iexfinance/>

url: <https://iexcloud.io/>
```bash
pip install iexfinance
```
To install NSEpy:

url: <https://nsepy.xyz/>
```bash
pip install nsepy
```
## Deployment

To deploy this project run

```bash
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  from datetime import datetime
  from pandas_datareader import data as wb
```

```bash
  from iexfinance.stocks import Stock, get_historical_data

  start = datetime(2018, 1, 1)
  end = datetime(2023, 3, 23)

  api_key = 'API_KEY'
```

Creating a portfolio:
```bash
tickers = ['Stocks']
mydata = pd.DataFrame()
for t in tickers:
    mydata[t] = get_historical_data(t, start, end, output_format = 'pandas', token=api_key)['close']
```
