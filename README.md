# Adaptive Momentum Trading Strategy with Machine Learning
This repository contains a sophisticated algorithmic trading strategy that combines momentum indicators, technical analysis, and machine learning to identify high-probability trading opportunities across multiple stocks.

<img width="361" alt="image" src="https://github.com/user-attachments/assets/a3811370-cd57-4099-93fd-3db38c5d7c45" />


# Overview
The strategy implements a comprehensive approach to market analysis:

Multiple Timeframe Momentum Analysis - Evaluates price performance across 1, 3, 6, 9, and 12-month periods
Technical Indicator Framework - Utilizes moving averages, volatility measures, and volume analysis
Machine Learning Signal Generation - Uses Random Forest classification to predict future price direction
Adaptive Risk Management - Dynamically adjusts position sizing and risk parameters based on volatility
Portfolio Optimization - Ranks opportunities across multiple stocks to allocate capital efficiently

<img width="499" alt="image" src="https://github.com/user-attachments/assets/02df2de2-bfc8-422a-b245-319ee9b93739" />

<img width="703" alt="image" src="https://github.com/user-attachments/assets/bad54bc5-d1a6-4116-b3a6-0f0427a2b4be" />

<img width="693" alt="image" src="https://github.com/user-attachments/assets/b042ecc5-7c14-48e8-ad15-39b428f5dbbc" />

The system is designed to adapt to changing market conditions while maintaining robust risk management principles.
Key Features

Data Retrieval: Fetches historical price data from Alpha Vantage API with rate limit handling
Feature Engineering: Calculates 15+ technical features including momentum, MA crossovers, and volatility regimes
Machine Learning Integration: Employs time-series cross-validation for model training
Adaptive Position Sizing: Adjusts position size based on volatility conditions
Dynamic Stop Loss/Take Profit: Sets risk parameters proportional to market volatility
Multi-Asset Portfolio Management: Manages up to 5 positions simultaneously based on opportunity ranking
Comprehensive Performance Analytics: Calculates metrics like Sharpe ratio, drawdown, win rate, and profit factor
Benchmark Comparison: Evaluates strategy performance against S&P 500

# Requirements

Python 3.6+
pandas
numpy
matplotlib
scikit-learn
requests
tqdm

Installation
bashCopypip install pandas numpy matplotlib scikit-learn requests tqdm
Usage

Set your Alpha Vantage API key:

pythonCopyALPHA_VANTAGE_API_KEY = 'YOUR_API_KEY'

Customize the list of symbols to analyze:

pythonCopySYMBOLS = ['AAPL', 'MSFT', 'GOOGL', ...]

Run the strategy:

pythonCopyperformance_results, all_trades, trade_recommendations = run_advanced_strategy_backtest()

View current trading recommendations:

pythonCopyfor rec in trade_recommendations:
    print(f"{rec['action']} {rec['symbol']} at ${rec['price']:.2f}")
Strategy Components
Signal Generation
The strategy generates signals through a weighted combination of:

Momentum Signals: Evaluates price momentum across multiple timeframes
Moving Average Signals: Analyzes price relative to key moving averages (20, 50, 100, 200-day)
Machine Learning Predictions: Uses Random Forest to predict future price direction

Risk Management

Adaptive Stop Loss: Automatically sizes stop loss based on recent volatility
Proportional Take Profit: Sets take profit targets with favorable risk-reward ratios (typically 1:2.5)
Position Sizing: Adjusts position size inversely proportional to volatility
Portfolio Diversification: Limits exposure across multiple positions

Performance Evaluation
The strategy calculates comprehensive performance metrics including:

Total and annualized returns
Maximum drawdown
Win rate and profit factor
Sharpe ratio
Comparison against S&P 500 benchmark

Example Output
The strategy produces:

Performance metrics for individual stocks and the overall portfolio
Comparison charts against S&P 500
Equity curve visualization
Ranked list of current trading opportunities with entry points, stop loss, and take profit levels

Limitations

Requires Alpha Vantage API key with sufficient quota
Execution assumes market orders at close prices
Historical backtesting does not account for slippage or commission
API rate limits may restrict the number of symbols that can be analyzed in one run
