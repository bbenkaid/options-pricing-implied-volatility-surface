# Options-pricing-implied-volatility-surface
Python project exploring quantitative finance through Black–Scholes option pricing, implied volatility estimation, volatility smile and surface construction, and variance swap pricing. Uses market data, numerical methods, and data visualization to investigate equity index and ETF options.

<img width="404" height="445" alt="image" src="https://github.com/user-attachments/assets/97e97a2e-5d91-4b51-83a7-2e507056e373" />
<img width="404" height="445" alt="image" src="https://github.com/user-attachments/assets/b18547a5-ee77-4770-8c73-04d7da54a108" />

Implied volatility inverted from call mid prices (Brent) across all strikes. The wings are noisy because deep ITM/OTM calls are illiquid; the variance swap strike is shown as the horizontal line.
<img width="404" height="445" alt="image" src="https://github.com/user-attachments/assets/5c16b3ec-4de6-4c64-adc0-e5fafc73a690" />

# Quantitative Finance in Python

A quantitative finance project focused on **option pricing, implied volatility analysis, volatility surfaces, and variance swaps**, using Python and market data.

## Overview

This project explores the relationship between theoretical option pricing models and observed market prices. It combines numerical methods, financial mathematics, and data visualization to study equity index and ETF options.

## Features

### 1. Market Data
- Retrieve historical underlying prices and option chains using `yfinance`.
- Extract call and put quotes, including bid, ask, and mid prices.
- Analyze option strikes and available expiration dates.

### 2. Black–Scholes Option Pricing
- Implement the Black–Scholes formula for European call options.
- Compare theoretical prices with observed market quotes.
- Calculate relative pricing errors.
- Estimate implied volatility by numerically inverting the Black–Scholes formula using Brent's method.

### 3. Volatility Analysis
- Calculate historical volatility from logarithmic returns.
- Compare historical volatility with implied volatility.
- Examine volatility smiles across option strikes.
- Build a three-dimensional implied volatility surface across strike and maturity, using log-forward moneyness and interpolation of total variance.

### 4. Variance Swaps
- Estimate the fair variance strike from out-of-the-money call and put prices.
- Convert the variance strike into its volatility-equivalent measure.
- Explore the relationship between option-implied variance and volatility.

## Technologies

- **Python**
- NumPy and pandas
- SciPy
- Matplotlib
- yfinance

## Methodology

The project uses the Black–Scholes model as a baseline for European option pricing and numerical root-finding to recover implied volatility from market prices.

The volatility surface is constructed from option-chain observations across available maturities. Total variance, \(w(k,T)=\sigma_{\mathrm{imp}}^2(k,T)T\), is interpolated over log-forward moneyness and maturity.

The variance swap section implements a discrete approximation to the option-based fair variance strike formula.

## Current Limitations

- Market quotes may be illiquid, stale, or affected by wide bid–ask spreads.
- The Black–Scholes implementation currently assumes a constant risk-free rate and does not explicitly model dividends.
- Surface interpolation depends on the quality and coverage of available option quotes.
- The discrete variance swap calculation requires careful treatment of strike spacing, the forward price, and the strike nearest the forward.
- Numerical outputs should be validated against market conventions and independent reference values.

## Go further


- [ ] **Implement SVI calibration:** fit each maturity and evaluate calibration quality using RMSE in volatility points.
- [ ] **Check static arbitrage:** test butterfly and calendar-spread arbitrage on the calibrated surface.
- [ ] **Price variance swaps:** implement option-based replication and validate results against the VIX.
- [ ] **Simulate delta hedging:** analyze hedging P&L and residual errors under different rebalancing frequencies.

## Author

Engineering student at Centrale Lyon interested in quantitative finance, derivatives pricing, and financial markets.
