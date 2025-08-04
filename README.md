# S&P 500 Next-Day Direction Prediction

## 🗂️ Project Overview

This notebook predicts the daily direction (up or down) of the S&P 500 index using historical price data and machine learning. The goal is to forecast whether the closing price tomorrow will be higher than today’s close.

We use a combination of technical features, a rolling backtest evaluation, and machine learning models (Random Forest and XGBoost).

---

## 📊 Key Features

Features include:

- **Basic price features:** Close, Volume, Open, High, Low.
- **Target:** Binary indicator if tomorrow’s closing price is higher than today’s.
- **Rolling features:** Ratios of Close price to rolling averages over multiple horizons (2, 50, 60, 250, 1000 days).
- **Trend features:** Sum of positive movements over rolling windows.
- **Volatility (Step 1):** 20-day rolling standard deviation of daily returns.
- **Momentum (Step 2):** Difference between today’s close and the close 10 days ago.

---

## ✅ Modeling

- **Models used:**
  - Random Forest Classifier
  - XGBoost Classifier

- **Backtesting:**
  - The data is split in an expanding window fashion.
  - The model is trained on past data and tested on the next chunk of data repeatedly.
  - This simulates a realistic forecasting scenario without lookahead bias.

---

---

## 🧠 Dataset

The dataset contains historical daily data of the S&P 500 index, downloaded using the `yfinance` library. It includes the following fields:

- **Date:** Trading date (index)
- **Open:** Opening price of the day
- **High:** Highest price during the day
- **Low:** Lowest price during the day
- **Close:** Closing price of the day
- **Volume:** Number of shares traded
- **Dividends:** Dividend payouts (removed before modeling)
- **Stock Splits:** Stock split events (removed before modeling)

The dataset spans multiple decades, but analysis begins from January 1, 1989, to ensure data quality and relevance.

---

## 🧪 Libraries Used

- **pandas:** Data manipulation and analysis
- **yfinance:** Downloading historical stock market data
- **matplotlib:** Plotting and visualization
- **scikit-learn:** Machine learning algorithms and metrics
- **xgboost:** Gradient boosting model (used as an alternative to Random Forest)

Make sure to install missing packages using `pip install package_name` if running the notebook locally.

---

## 🔍 Future Improvements

- **Threshold optimization:** Instead of a fixed threshold (0.6) for classification, tune it to maximize precision or other metrics.
- **Additional features:** Incorporate technical indicators like RSI, MACD, Bollinger Bands, and volume-based signals.
- **Time-series aware validation:** Use `TimeSeriesSplit` for more realistic model validation.
- **Longer prediction horizons:** Predict price movement over multiple days instead of just the next day to reduce noise.
- **External data:** Add macroeconomic indicators, news sentiment, or alternative data sources.
- **Hyperparameter tuning:** Use `GridSearchCV` or `RandomizedSearchCV` to find optimal model parameters.
- **Deployment:** Wrap the model into an API or dashboard for live predictions.

---

## 📁 Files

| File | Description |
|------|-------------|
| `StockAnalysis.ipynb` | Full analysis and model notebook |
| `sp500.csv`       | Raw or sample data |
| `README.md`              | This project description |


---

## Author

**Your Name**  
Email: your.email@example.com  
GitHub: [your-github-username](https://github.com/your-github-username)  
LinkedIn: [your-linkedin-profile](https://linkedin.com/in/your-linkedin-profile)  

*Feel free to reach out for questions, suggestions, or collaborations!*

---

