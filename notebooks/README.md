# Financial Market ML Notebooks

This directory contains the Jupyter Notebook implementation of the postgraduate Financial Market Machine Learning Trading System.

## Analytical Pipeline

The implementation covers:

- Multi-asset financial data loading
- Bid/ask data integration
- Mid-price calculation
- Data cleaning and preprocessing
- Feature scaling
- Financial feature engineering
- Technical indicators
- Candlestick structure features
- Market-regime features
- BUY / HOLD / SELL target generation
- Time-series sequence creation
- CNN training and evaluation
- LSTM training and evaluation
- MLP training and evaluation
- Random Forest benchmarking
- Ensemble modelling
- Class-imbalance handling
- Backtesting with transaction costs
- Sharpe ratio, maximum drawdown and win-rate evaluation
- Statistical testing
- Feature importance and ablation analysis
- Walk-forward validation

## Models

The project evaluates several modelling approaches:

### CNN
Designed to identify local and short-term patterns within financial time-series sequences.

### LSTM
Designed to capture longer-term temporal dependencies and sequential market behaviour.

### MLP
Used as a simpler neural-network baseline for comparison with sequential architectures.

### Random Forest
Used as a traditional machine-learning benchmark.

### Ensemble
Combines predictions from multiple models to investigate whether model diversity can improve robustness.

## Target Classes

The prediction task is formulated as a three-class classification problem:

- BUY
- HOLD
- SELL

## Evaluation

Models are evaluated using both machine-learning and financial-performance measures.

Financial evaluation includes:

- Sharpe ratio
- Maximum drawdown
- Win rate
- Backtested returns
- Transaction-cost sensitivity

Walk-forward validation is used to provide a more realistic assessment of model generalisation across changing market conditions.

## Disclaimer

This implementation was developed for postgraduate academic research and portfolio demonstration.

It is not a live trading system, investment recommendation or financial advice. Historical and simulated performance does not guarantee future performance.
