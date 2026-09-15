# Data

This directory documents the financial market datasets used in the Financial Market Machine Learning Trading System.

## Data Source

Historical financial market data was obtained from Dukascopy for postgraduate academic research.

The project uses historical bid and ask OHLC market data across multiple asset classes.

## Markets

The research includes datasets representing:

- Equity index market
- Cryptocurrency market
- Gold / commodity market
- Foreign exchange market

Dataset identifiers used in the research include:

- S&P 500-labelled dataset
- BCHUSD
- XAUUSD
- GBPUSD

Different sampling intervals were used across the instruments to evaluate model behaviour under different market conditions.

## Raw Data Structure

The original market files contain fields such as:

- Time
- Open
- High
- Low
- Close
- Volume

Bid and ask datasets are combined during preprocessing.

## Preprocessing

The preprocessing pipeline includes:

1. Loading historical bid and ask market data
2. Parsing timestamps
3. Merging bid and ask observations
4. Calculating mid-price OHLC values
5. Handling missing, duplicate and infinite values
6. Generating financial and technical features
7. Scaling numerical features using training data
8. Generating BUY, HOLD and SELL target classes
9. Creating sequential observations for model training

## Feature Engineering

Engineered features include:

- Candlestick body
- Candle range
- Upper wick
- Lower wick
- Body ratio
- Price direction
- EMA 12
- EMA 26
- MACD
- MACD signal
- Alligator indicators
- Stochastic oscillators
- Rolling volatility
- Average True Range
- Cyclical time features
- Market-regime features

## Data Leakage Prevention

Scaling parameters are fitted using the training dataset rather than the complete dataset to reduce the risk of information leakage from validation or test observations.

## Repository Data Policy

The complete raw historical market datasets are not stored in this repository.

This keeps the repository lightweight and avoids unnecessarily redistributing large third-party historical market-data files.

The notebook demonstrates the preprocessing, feature-engineering, modelling and evaluation methodology used in the postgraduate research project.

## Disclaimer

The datasets and resulting analyses are used for academic research and portfolio demonstration only.

Nothing in this repository constitutes financial or investment advice.
