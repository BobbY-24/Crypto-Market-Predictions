# Crypto Market Open-Close Prediction

## Overview
This project analyzes cryptocurrency open and close price data and models the difference between closing and opening prices. It compares linear regression and Random Forest regression on a single cryptocurrency price dataset. The project is a compact time-series-flavored regression exercise, not a production trading system.

## Motivation
Financial prediction tasks are useful for learning feature engineering, regression evaluation, and the dangers of overinterpreting noisy markets. This project demonstrates model comparison and metric reporting while also showing why market prediction requires careful validation.

## Dataset
- **Source:** TODO: document original data source.
- **File:** `data/1inch-usd.csv`
- **Target variable:** `closing_difference`, calculated as closing price minus opening price.
- **Important features:** open price, close price, and available market/time fields.
- **Dataset size:** TODO: add dataset size after rerunning notebook.
- **Known limitations:** Cryptocurrency data is noisy, non-stationary, and highly sensitive to time leakage.

## Methods
- Loaded cryptocurrency price data.
- Created a `closing_difference` target.
- Trained Linear Regression and Random Forest Regressor models.
- Evaluated using RMSE and R-squared.

## Results
The notebook reports:

| Model | RMSE | R-squared |
| --- | ---: | ---: |
| Linear Regression | 0.0009 | 0.9222 |
| Random Forest Regressor | 0.0032 | 0.0088 |

## Key Insights
- Linear Regression performed much better than Random Forest in the reported experiment.
- The result may reflect target construction, leakage, or a simple linear relationship in the selected fields.
- Strong financial metrics should be treated cautiously without temporal validation.

## Limitations
- The project does not yet use a proper time-based train/test split.
- It does not account for transaction costs, slippage, or live trading constraints.
- Results from one cryptocurrency do not generalize to the market.
- This is a learning project and should not be used for investment decisions.

## Future Improvements
- Use time-series cross-validation.
- Add lagged features and compare against naive baselines.
- Evaluate multiple cryptocurrencies.
- Add leakage checks and a clear train/test date split.

## How to Run
```bash
git clone https://github.com/BobbY-24/Crypto-Market-Predictions.git
cd Crypto-Market-Predictions
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/crypto_market_open_close_analysis.ipynb
```
