# 📈 Financial Market Machine Learning Trading System

### Multi-Asset Time-Series Classification, Deep Learning & Backtesting

A postgraduate MSc Computer Science research project investigating whether machine learning and deep learning models can identify short-term patterns in financial time-series data and translate those predictions into economically meaningful **BUY, HOLD and SELL signals**.

The project develops an end-to-end research pipeline covering data preprocessing, financial feature engineering, model training, classification, backtesting, benchmark comparison, transaction-cost analysis, statistical testing and walk-forward validation.

---

## 🎯 Project Objective

Financial markets are noisy, non-stationary and difficult to predict consistently.

This project investigates whether different machine-learning architectures can extract useful predictive information from historical multi-asset market data and whether classification performance translates into meaningful risk-adjusted trading performance.

The research compares model effectiveness across different market types rather than assuming that one architecture will perform equally well everywhere.

---

## 🔬 Research Questions

The project investigates questions including:

- Can deep-learning models outperform traditional trading strategies?
- Which architecture performs best for financial time-series prediction?
- Does feature engineering improve model performance?
- Are generated strategy returns statistically significant?
- How sensitive are strategies to transaction costs?
- Does walk-forward validation provide more realistic generalisation testing?
- Which feature groups contribute most to predictive performance?

---

## 🌍 Markets Analysed

The research evaluates four financial-market datasets across different asset classes and timeframes:

| Market | Asset Class | Timeframe |
|---|---|---:|
| S&P 500-labelled dataset | Equity Index | 5 min |
| BCHUSD | Cryptocurrency | 10 min |
| XAUUSD | Gold / Commodity | 15 min |
| GBPUSD | Foreign Exchange | 30 min |

Historical bid/ask market data was obtained from Dukascopy and processed into modelling-ready time-series datasets.

---

## 🧠 Models Evaluated

The research evaluates multiple machine-learning approaches:

- **Long Short-Term Memory (LSTM)** — sequential deep-learning architecture
- **Convolutional Neural Network (CNN)** — local temporal pattern extraction
- **Multi-Layer Perceptron (MLP)** — feed-forward neural network
- **Random Forest** — traditional machine-learning benchmark
- **Ensemble modelling** — combined model predictions

This multi-model approach allowed model behaviour to be compared across markets with different characteristics.

---

## ⚙️ End-to-End Pipeline

```text
Historical Bid/Ask Data
        ↓
Data Cleaning & Synchronisation
        ↓
Mid-Price Construction
        ↓
Feature Engineering
        ↓
Technical Indicators
        ↓
Market-Regime Features
        ↓
Train / Validation / Test Separation
        ↓
Training-Only Feature Scaling
        ↓
128-Step Time-Series Sequences
        ↓
CNN / LSTM / MLP / RF / Ensemble
        ↓
BUY / HOLD / SELL Predictions
        ↓
Backtesting
        ↓
Transaction-Cost Adjustment
        ↓
Financial Performance Evaluation
        ↓
Benchmark & Statistical Testing
        ↓
Walk-Forward Validation
```

---

## 🛠 Feature Engineering

The modelling pipeline incorporates price, technical, temporal and volatility information, including:

- Candlestick body and range
- Upper and lower wick
- Body ratio and price direction
- EMA 12 and EMA 26
- MACD and signal line
- Alligator indicator
- Stochastic oscillators
- Rolling volatility
- Average True Range (ATR)
- Cyclical time features
- Market-regime information

Feature scaling is fitted using training data only to reduce the risk of data leakage.

---

## 🎯 Prediction Framework

The processed market data is transformed into sequential observations using:

- **Sequence length:** 128 timesteps
- **Forecast horizon:** 6 steps ahead
- **Target classes:** BUY / HOLD / SELL

The models therefore learn from historical sequences before predicting future price-direction classes.

---

## ⚖️ Handling Class Imbalance

Financial-market direction classes are naturally imbalanced.

The project addresses this using:

- Class weighting
- Focal loss
- Early stopping

This reduces the tendency of neural networks to optimise primarily for the dominant class.

---

## 📊 Evaluation Framework

Model performance is evaluated using both machine-learning and financial metrics.

### Classification Evaluation

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrices

### Financial Evaluation

- Sharpe Ratio
- Maximum Drawdown
- Win Rate
- Equity Curve
- Trade Returns
- Transaction Costs

Classification accuracy alone is not treated as evidence of a successful trading strategy.

---

## 🏆 Selected Results

Model performance varied substantially across instruments.

| Model / Dataset | Sharpe Ratio | Key Finding |
|---|---:|---|
| LSTM — S&P 500-labelled dataset | **1.876** | Strongest result in the research |
| MLP — BCHUSD | **1.689** | Strong performance despite simpler architecture |
| MLP — S&P 500-labelled dataset | -0.811 | Negative risk-adjusted performance |
| MLP — XAUUSD | -3.637 | Underperformed |
| MLP — GBPUSD | -0.154 | Weak financial performance |

The LSTM produced the strongest recorded result on the S&P 500-labelled dataset, while the MLP performed particularly well on BCHUSD.

The results demonstrate that **model complexity alone does not determine financial performance**.

---

## 📉 CNN Findings

The CNN produced negative Sharpe ratios across the evaluated datasets:

| Dataset | Sharpe Ratio |
|---|---:|
| S&P 500-labelled dataset | -4.149 |
| BCHUSD | -2.885 |
| XAUUSD | -2.193 |
| GBPUSD | -0.299 |

This provided an important negative result: architectures that are effective in other machine-learning domains do not necessarily transfer successfully to noisy financial time-series environments.

---

## 🥇 LSTM Performance

The strongest result in the research was produced by the LSTM on the S&P 500-labelled dataset.

![LSTM vs Baseline](results/screenshots/01-lstm-vs-baseline.png)

### Classification Performance

![LSTM Classification Report](results/screenshots/02-lstm-classification-report.png)

### Equity Curve

![LSTM Equity Curve](results/screenshots/03-lstm-equity-curve.png)

---

## 📊 Benchmark Comparison

Machine-learning models were compared with traditional strategies including:

- Buy & Hold
- Moving Average strategy

Importantly, machine learning did **not** outperform the benchmarks on every market.

For XAUUSD, Buy & Hold achieved a Sharpe ratio of **0.44**, outperforming the evaluated machine-learning models.

![Gold vs Baseline](results/screenshots/04-gold-vs-baseline.png)

This highlights the importance of benchmark comparison rather than evaluating predictive models in isolation.

---

## 🔍 Ablation Study & Feature Importance

An ablation study was conducted by removing feature groups and retraining the models.

The analysis found that technical indicators and price-based features contributed meaningfully to model performance.

MACD and stochastic oscillators contributed to trend and momentum detection, while price-structure features captured additional market behaviour.

Candlestick-pattern features had comparatively limited impact.

![Ablation Study](results/screenshots/05-ablation-study.png)

---

## 🔎 Error Analysis

Model errors were analysed across different market regimes.

The models generally performed better during directional bullish and bearish conditions, while higher error rates occurred during sideways or neutral markets.

A regime-filtering mechanism was used to reduce trades that contradicted the prevailing market trend.

![Error Analysis](results/screenshots/06-error-analysis.png)

---

## 🚶 Walk-Forward Validation

Walk-forward validation was implemented to provide a more realistic test of model generalisation.

Instead of relying only on a conventional random train/test split, the model:

1. Trains on a historical window.
2. Tests on the immediately following unseen period.
3. Moves the window forward.
4. Retrains the model.
5. Repeats the evaluation.

This preserves temporal ordering and helps reduce unrealistic evaluation caused by future-data leakage.

Performance varied across windows as market conditions changed, illustrating the non-stationary nature of financial markets.

---

## 💰 Transaction-Cost Analysis

Transaction costs were incorporated into backtesting to avoid overstating strategy performance.

This is particularly important for intraday strategies where frequent trading can turn apparently profitable predictions into economically weak strategies after costs.

---

## 📐 Statistical Testing

Strategy returns were evaluated using statistical testing to investigate whether observed average returns differed significantly from zero.

The project distinguishes between **statistical significance and economic significance**: statistically significant predictions are not necessarily sufficiently profitable after costs and risk.

---

## 💡 Key Research Findings

The project demonstrates that:

- No single machine-learning architecture performs best across every financial market.
- LSTM showed strong performance where useful temporal structure was present.
- A simpler MLP performed strongly on BCHUSD.
- CNN performance was weak across the evaluated datasets.
- Feature engineering can be as important as model complexity.
- Classification accuracy alone is insufficient for evaluating trading systems.
- Transaction costs materially affect strategy viability.
- Traditional benchmarks can outperform machine-learning models.
- Market regime influences predictive performance.
- Walk-forward validation provides a more realistic robustness assessment.

---

## 💻 Technology Stack

**Programming & Analysis**

- Python
- Jupyter Notebook
- pandas
- NumPy
- SciPy

**Machine Learning**

- TensorFlow
- Keras
- scikit-learn

**Visualisation**

- Matplotlib
- Seaborn

**Methods**

- Financial Time-Series Analysis
- Deep Learning
- Feature Engineering
- Classification
- Backtesting
- Statistical Testing
- Walk-Forward Validation

---

## 📁 Repository Structure

```text
financial-market-ml-trading-system/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   └── README.md
│
├── docs/
│   ├── README.md
│   └── Financial_Market_ML_Trading_System_Postgraduate_Project.pdf
│
├── notebooks/
│   ├── README.md
│   └── Financial_Market_ML_Trading_System.ipynb
│
└── results/
    ├── README.md
    └── screenshots/
        ├── README.md
        ├── 01-lstm-vs-baseline.png
        ├── 02-lstm-classification-report.png
        ├── 03-lstm-equity-curve.png
        ├── 04-gold-vs-baseline.png
        ├── 05-ablation-study.png
        └── 06-error-analysis.png
```

---

## 🚀 Running the Project

Clone the repository:

```bash
git clone <repository-url>
cd financial-market-ml-trading-system
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

Launch Jupyter:

```bash
jupyter notebook
```

Then open:

```text
notebooks/Financial_Market_ML_Trading_System.ipynb
```

> The complete raw third-party market datasets are not distributed in this repository. See `data/README.md` for information about the data structure, source and preprocessing workflow.

---

## 📄 Full Postgraduate Report

The complete academic report covering the research background, methodology, implementation, experiments, results, discussion, limitations and future work is available at:

`docs/Financial_Market_ML_Trading_System_Postgraduate_Project.pdf`

---

## 🎓 Skills Demonstrated

This project demonstrates practical experience in:

**Python • Machine Learning • Deep Learning • TensorFlow/Keras • scikit-learn • Financial Time-Series Analysis • Feature Engineering • Model Evaluation • Backtesting • Statistical Analysis • Walk-Forward Validation • Data Leakage Prevention • Research & Technical Documentation**

---

## ⚠️ Disclaimer

This repository contains an academic research prototype developed as part of a postgraduate Computer Science project.

The models and backtesting results are based on historical data and simulated experiments. They do not represent live trading performance, guaranteed returns or financial advice.
