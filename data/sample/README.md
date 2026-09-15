
# Sample Market Data

This directory contains a small sample of the historical financial-market data used in the postgraduate machine-learning project.

## Sample Dataset

`sample_bchusd_10min_ask.csv`

The file contains **250 observations** from the BCHUSD 10-minute Ask dataset used in the research.

The sample preserves the structure of the original dataset:

- `Time (EET)`
- `Open`
- `High`
- `Low`
- `Close`
- `Volume`

## Purpose

The complete raw market datasets are not distributed in this repository.

This sample is provided so that recruiters, reviewers and developers can:

- inspect the original input-data structure;
- understand the OHLCV format used by the pipeline;
- see the type of financial time-series data used during preprocessing; and
- better understand how the Jupyter Notebook transforms raw market data into modelling-ready features.

## Full Data Pipeline

The complete project used historical bid and ask market data. During preprocessing, corresponding bid and ask observations were synchronised before additional price and technical features were generated for machine-learning modelling.

See the main `data/README.md` for further information about data sourcing, preprocessing and feature engineering.

## Disclaimer

The sample is provided solely for academic, technical demonstration and portfolio purposes. It should not be interpreted as current market information or financial advice.
