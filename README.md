Volatility-Based Algorithmic Trading Bot

A Python-based automated trading framework focusing on volatility trend-following and dynamic risk management.

Project Overview

This project implements a quantitative trading strategy that utilizes Average True Range (ATR) to detect market volatility regimes. It includes a full backtesting engine and an execution module connected to crypto exchange APIs.

Key Features:

Volatility Filter: Automatically pauses trading when BTC ATR (14-day) exceeds a threshold (0.04), mitigating drawdown during extreme turbulence.

Dynamic Hedging: Executes short positions on BTC/ETH to hedge against systemic risk when longing high-beta altcoins.

Risk Management: Built-in STOP_LOSS (-2%) and TAKE_PROFIT (+2%) logic per trade.

Technical Stack

Language: Python 3.9+

Libraries: pandas, numpy (Data Analysis), ccxt / alpaca-trade-api (Execution), matplotlib (Visualization)

Data Source: Historical OHLCV data from major CEXs.

Strategy Performance & Optimization

(Refer to the attached Strategy_Optimization_Report.pdf for full details)

1. Volatility Analysis (ATR)

We identified a negative correlation between high ATR and strategy returns.

Low Volatility (< 0.03 ATR): Stable positive returns.

High Volatility (> 0.04 ATR): Significant performance degradation.

Optimization: Implemented a circuit breaker to halt entries when BTC_ATR > 0.04.

2. Hedging Impact

Backtesting confirmed that simultaneous shorting of BTC/ETH during altcoin entries significantly smoothed the equity curve and reduced Max Drawdown.
