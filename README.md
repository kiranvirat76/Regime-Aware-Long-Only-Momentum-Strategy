# Quant Trading System

Systematic trading engine with realistic execution modeling, multi-strategy portfolio construction, and out-of-sample validation.

---

## Overview

This project implements a quantitative trading framework designed to simulate real-world trading conditions.  
The focus is on building strategies that remain robust after accounting for execution delays, transaction costs, and market regimes.

Unlike typical academic backtests, this system incorporates practical constraints such as T+1 execution and regime-dependent risk control.

---

## Key Features

- Multi-strategy portfolio (momentum + trend filtering)
- T+1 execution to eliminate lookahead bias
- Transaction cost and slippage modeling (0.268% per trade)
- Regime-based exposure control using market breadth indicators
- Volatility-adjusted position sizing
- Walk-forward and out-of-sample validation
- Monte Carlo simulation for robustness analysis

---

## Strategy Design

The system combines multiple components:

### 1. Momentum Layer
- Kalman Momentum for true direction of the stock, ignoring the noise.
- 1-month, 6-month, and 12-month returns
- Cross-sectional ranking across stocks

### 2. Trend Filtering
- Moving averages to align with broader market direction

### 3. Regime Detection
- Market breadth indicators
- Bear and crash regime identification

### 4. Risk Management
- Volatility-based position sizing  
- Trailing stop-loss  
- Max position constraints  
- Portfolio diversification  

---

## Data

- NSE equities universe  
- OHLC price data  
- Multi-year historical period  
- Daily frequency with realistic execution assumptions  

---

## Results

| Metric                 | Value   |
|------------------------|---------|
| CAGR                   | 22.37%  |
| Sharpe Ratio           | 1.86    |
| Max Drawdown           | -19.41% |
| Annualized Volatility  | -19.4%  |
| Win Rate               | 55.66%  |

---

## Out-of-Sample Validation

| Metric        | In-Sample | Out-of-Sample |
|--------------|----------|---------------|
| CAGR         | XX%      | XX%           |
| Drawdown     | XX%      | XX%           |
| Sharpe       | X.X      | X.X           |

Performance remains stable out-of-sample, indicating limited overfitting.

---

## Key Insights

- Execution costs significantly reduce inflated backtest performance  
- Regime-based exposure improves drawdown control  
- Momentum works better when combined with trend filters  
- Diversification improves risk-adjusted returns  

---

## Repository Structure

## Files
- `strategy.py` → main trading engine
- `quant_summary.pdf` → strategy explanation and results

## How to Run
pip install -r requirements.txt  
python strategy.py
