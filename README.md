# Financial-Market-Regime-Detection-and-Risk-Modelling


AI-based financial market regime detection using **K-Means Clustering** and **Hidden Markov Models (HMM)** on S&P 500 time series data.

---

# Overview

Financial markets do not behave uniformly over time. Markets move through different phases such as:

- Bull Markets → Positive returns and low volatility
- Normal Markets → Moderate returns and moderate risk
- Crisis Markets → High volatility and negative returns

This project applies **unsupervised machine learning** techniques to identify hidden market regimes from historical financial data and uses them to build a **regime-aware investment strategy**.

The study demonstrates that adapting investment decisions according to detected market conditions can significantly reduce risk and improve performance compared to a traditional buy-and-hold strategy.

---

# Objectives

- Analyze financial time series using returns, volatility, and drawdowns
- Detect hidden market regimes using AI/ML techniques
- Study transitions and persistence between regimes
- Build a regime-based investment strategy
- Compare performance against a buy-and-hold strategy

---

# Dataset

- **Dataset:** S&P 500 Index
- **Source:** Yahoo Finance (`yfinance`)
- **Period:** January 2001 – January 2025
- **Frequency:** Daily Data

The dataset includes major financial events such as:

- Dot-com crash
- 2008 Global Financial Crisis
- COVID-19 crash

---

# Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- hmmlearn
- yfinance

---

# Feature Engineering

The following financial features were constructed from raw price data:

## 1. Log Returns

Measures percentage price changes over time.

## 2. Volatility

Rolling standard deviation of returns using a 20-day window.

## 3. Drawdown

Measures decline from historical peak.

## 4. Rolling Features

Used to capture short-term and long-term market behaviour.

---

# Machine Learning Models

# 1. K-Means Clustering

K-Means was used as an initial unsupervised learning method to group similar market conditions.


## Identified Regimes

| Regime | Interpretation |
|--------|----------------|
| Regime 1 | Bull Market |
| Regime 0 | Normal Market |
| Regime 2 | Crisis Market |

## Key Findings

- Bull regimes showed positive returns and low volatility
- Crisis regimes showed high volatility and large drawdowns
- Major market crashes aligned with crisis clusters

---

# 2. Hidden Markov Model (HMM)

Unlike K-Means, HMM captures **time dependence** and **state transitions** between market regimes.

## Why HMM?

Markets evolve gradually over time and regimes tend to persist. HMM models this behaviour using hidden states and transition probabilities.


## Key Insights

- Regimes are highly persistent
- Crisis regimes tend to last longer
- Market behaviour changes gradually over time

---

# Investment Strategy

A simple regime-based strategy was developed using HMM regimes.

## Strategy Rules

| Market Regime | Action |
|---------------|--------|
| Bull Regime | Invest in market |
| Normal Regime | Stay in cash |
| Crisis Regime | Stay in cash |

The strategy attempts to avoid large drawdowns during turbulent periods.
---

# Performance Metrics

The following metrics were used:

- Total Return
- Volatility
- Sharpe Ratio
- Maximum Drawdown

---

# Performance Comparison

| Metric | Buy & Hold | Regime Strategy |
|--------|-------------|----------------|
| Total Return | 207.8% | 337.9% |
| Volatility | 19.2% | 4.9% |
| Sharpe Ratio | 0.35 | 1.30 |
| Maximum Drawdown | -61.0% | -4.5% |

---

# Key Results

The regime-based strategy:

- Achieved higher cumulative returns
- Reduced volatility significantly
- Improved risk-adjusted performance
- Avoided major market crashes

---
