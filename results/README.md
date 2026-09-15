# Model Results & Evaluation

This directory summarises the experimental results from the Financial Market Machine Learning Trading System.

The project evaluates machine-learning and deep-learning models across multiple financial-market datasets using both predictive and financial-performance measures.

## Models Evaluated

- Convolutional Neural Network (CNN)
- Long Short-Term Memory Network (LSTM)
- Multi-Layer Perceptron (MLP)
- Random Forest benchmark
- Ensemble modelling

## Evaluation Framework

Model performance was assessed using classification metrics alongside financial and statistical evaluation, including:

- Classification accuracy
- Sharpe ratio
- Maximum drawdown
- Win rate
- Backtested strategy performance
- Transaction-cost sensitivity
- Statistical significance testing
- Ablation analysis
- Error analysis
- Walk-forward validation
- Benchmark comparison

## Key Research Findings

### LSTM

The strongest recorded overall result was produced by the LSTM model on the S&P 500-labelled dataset, achieving a Sharpe ratio of approximately **1.88**.

This suggests that temporal dependencies within this dataset were better captured by the recurrent architecture than by several alternative models evaluated in the study.

### MLP

The MLP demonstrated particularly strong performance on the BCHUSD dataset, achieving a Sharpe ratio of approximately **1.69**.

This result shows that model effectiveness varied substantially across different financial instruments.

### CNN

The CNN produced negative Sharpe ratios across the evaluated datasets.

This was an important research finding because it demonstrated that greater model complexity did not automatically translate into superior trading performance.

### Gold / XAUUSD

For the gold dataset, the Buy & Hold benchmark achieved a Sharpe ratio of approximately **0.44** and outperformed the machine-learning models evaluated.

### GBPUSD

The machine-learning models produced negative Sharpe ratios on the GBPUSD dataset, while the Buy & Hold benchmark performed better.

This highlights the importance of comparing predictive models against simple financial benchmarks rather than assuming machine learning will outperform traditional strategies.

## Selected Model Results

| Dataset | Model | Sharpe Ratio | Key Observation |
|---|---|---:|---|
| S&P 500-labelled dataset | LSTM | 1.8757 | Strongest recorded overall result |
| BCHUSD | MLP | 1.689 | Strong performance on cryptocurrency dataset |
| XAUUSD | Buy & Hold | 0.44 | Benchmark outperformed ML models |
| GBPUSD | ML models | Negative | Benchmark performed better |

## MLP Results

| Dataset | Sharpe Ratio | Accuracy | Maximum Drawdown | Win Rate |
|---|---:|---:|---:|---:|
| IUFSUUSD_5M | -0.811 | 0.48 | -0.02266 | 0.0553 |
| BCHUSD_10M | 1.689 | 0.37 | -0.00859 | 0.3871 |
| XAUUSD_15M | -3.637 | 0.33 | -0.03785 | 0.1652 |
| GBPUSD_30M | -0.154 | 0.58 | -0.00144 | 0.0090 |

## CNN Sharpe Ratios

| Dataset | Sharpe Ratio |
|---|---:|
| IUFSUUSD_5M | -4.149 |
| BCHUSD_10M | -2.885 |
| XAUUSD_15M | -2.193 |
| GBPUSD_30M | -0.299 |

## Ablation Analysis

The ablation study showed that technical indicators and price-based features contributed meaningfully to model performance.

MACD and stochastic features contributed useful trend and momentum information.

Candlestick-pattern features showed more limited impact compared with several other engineered feature groups.

Cyclical time features also contributed useful information.

## Error Analysis

The models generally performed better during directional bullish and bearish market regimes.

Higher prediction errors were observed during sideways or neutral market conditions.

The use of market-regime filtering helped reduce contradictory trading signals.

## Walk-Forward Validation

Walk-forward evaluation demonstrated that performance varied across different market periods.

This variation illustrates the non-stationary nature of financial markets and the importance of evaluating models across changing market conditions rather than relying on a single train/test split.

## Research Interpretation

A central finding of this project is that no single machine-learning architecture consistently dominated across every financial instrument.

The experiments demonstrate that:

- model performance is instrument-dependent;
- strong classification accuracy does not necessarily imply strong trading performance;
- transaction costs materially affect strategy results;
- simple benchmarks can outperform complex machine-learning models;
- financial-market regime changes affect model generalisation;
- realistic validation is essential when evaluating financial ML systems.

These findings are as important as the project's strongest model results because they demonstrate critical evaluation rather than selective reporting of profitable experiments.

## Disclaimer

These results originate from postgraduate academic research using historical and simulated trading experiments.

They do not represent live trading performance, guaranteed returns or financial advice.
