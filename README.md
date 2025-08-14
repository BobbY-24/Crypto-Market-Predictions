Crypto Market Price Difference Prediction
📌 Project Overview

This project analyzes cryptocurrency market data to predict the price difference between opening and closing values for multiple cryptocurrencies.
A new feature called closing_difference is created, calculated as:

𝑐
𝑙
𝑜
𝑠
𝑖
𝑛
𝑔
_
𝑑
𝑖
𝑓
𝑓
𝑒
𝑟
𝑒
𝑛
𝑐
𝑒
=
𝑐
𝑙
𝑜
𝑠
𝑖
𝑛
𝑔
_
𝑝
𝑟
𝑖
𝑐
𝑒
−
𝑜
𝑝
𝑒
𝑛
𝑖
𝑛
𝑔
_
𝑝
𝑟
𝑖
𝑐
𝑒
closing_difference=closing_price−opening_price

We compare two machine learning models — Linear Regression and Random Forest Regressor — to evaluate their ability to predict this difference.

📂 Dataset

The dataset contains historical cryptocurrency market data with the following key columns:

currency – Name of the cryptocurrency (e.g., Bitcoin, Ethereum, etc.)

date – Trading date

open – Opening price

close – Closing price

volume – Trading volume

closing_difference – Derived feature: close - open

⚙️ Methods

Data Preprocessing

Handled missing values (if any)

Encoded categorical variables (currency)

Created the closing_difference feature

Split data into training and testing sets

Machine Learning Models

Linear Regression

Random Forest Regressor

Evaluation Metrics

Root Mean Squared Error (RMSE)

Coefficient of Determination (R²)

📊 Results
Model	RMSE	R²
Linear Regression	0.0009	0.9222
Random Forest	0.0032	0.0088
🧾 Conclusion

Linear Regression significantly outperformed Random Forest for this task, achieving an R² of 0.9222, indicating that it explains over 92% of the variance in the closing_difference.

Random Forest Regressor underperformed, suggesting that simpler, linear relationships dominate in this dataset, and non-linear ensemble methods may not be as effective without additional feature engineering.

🚀 Future Improvements

Add more market indicators such as moving averages, volatility, and sentiment scores.

Use time-series forecasting models like LSTM or Prophet to capture temporal dependencies.

Expand to multiple time horizons (1-day, 7-day, 30-day difference predictions).

📦 Dependencies

Python 3.x

pandas

numpy

scikit-learn

matplotlib / seaborn (for visualization)
