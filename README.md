# Crypto Market Open-Close Prediction

## Overview
I analyzed cryptocurrency open and close price data and modeled the difference between closing and opening prices. I compared linear regression and Random Forest regression on a single cryptocurrency price dataset.

## Motivation
I used this project to practice feature engineering, regression evaluation, and cautious interpretation in noisy financial data. I do not present it as a trading system.

## Dataset
- **File:** `data/1inch-usd.csv`
- **Target variable:** `closing_difference`, calculated as closing price minus opening price.
- **Important features:** open price, close price, and available market/time fields.
- **Known limitations:** Cryptocurrency data is noisy, non-stationary, and highly sensitive to time leakage.

## Methods
- I loaded cryptocurrency price data.
- I created a `closing_difference` target.
- I trained Linear Regression and Random Forest Regressor models.
- I evaluated the models using RMSE and R-squared.

## Results
| Model | RMSE | R-squared |
| --- | ---: | ---: |
| Linear Regression | 0.0009 | 0.9222 |
| Random Forest Regressor | 0.0032 | 0.0088 |

## Key Insights
- Linear Regression performed much better than Random Forest in the reported experiment.
- The result may reflect target construction, leakage, or a simple linear relationship in the selected fields.
- Financial metrics need time-aware validation before they mean much.

## Limitations
- I do not use a proper time-based train/test split yet.
- I do not account for transaction costs, slippage, or live trading constraints.
- Results from one cryptocurrency do not generalize to the market.
- I treat this as a learning project, not investment advice.

## How to Run
```bash
git clone https://github.com/BobbY-24/Crypto-Market-Predictions.git
cd Crypto-Market-Predictions
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/crypto_market_open_close_analysis.ipynb
```
