# Stock Price Prediction Tool

# StockForecast AI

## A machine learning-powered stock price forecasting tool

---

## 📈 Overview

StockForecast AI is a sophisticated Python application that leverages machine learning to predict potential future stock price movements. Built on a Random Forest Regressor model with adaptive technical indicators, this tool provides both numerical forecasts and visual representations of predicted stock trajectories.

While financial markets inherently involve uncertainty, StockForecast AI serves as an educational demonstration of applied data science and machine learning techniques in financial analysis.

---

## ✨ Key Features

- **Intelligent Data Acquisition**
  - Seamless historical stock data retrieval via Yahoo Finance API
  - Flexible time period selection (days to decades)
  - Robust error handling for API connectivity issues

- **Advanced Technical Analysis**
  - Dynamic calculation of technical indicators with adaptive window sizes
  - Feature engineering tailored to available historical data length
  - Comprehensive indicators including Moving Averages, Volatility, and Returns

- **Machine Learning Prediction Engine**
  - Random Forest Regression model optimized for time series data
  - Day-by-day iterative prediction methodology
  - Pattern recognition from historical price movements

- **Visualization & Reporting**
  - Elegant console output of recent and predicted prices
  - High-resolution visualization comparing historical data with forecasts
  - Automatic PNG export of prediction charts

---

## 🔧 Architecture

### Core Components

| Component | Description |
|-----------|-------------|
| Data Acquisition | Fetches and processes historical stock data through `yfinance` |
| Feature Engineering | Calculates adaptive technical indicators relevant to price prediction |
| Model Training | Implements and trains the Random Forest machine learning model |
| Prediction Engine | Performs iterative forecasting of future price movements |
| Visualization | Generates publication-quality charts of predictions |

### File Structure

- **`stock_price_prediction.py`**: Main application code
- **`test_stock_price_prediction.py`**: Comprehensive test suite
- **`requirements.txt`**: Dependencies specification
- **`README.md`**: Project documentation (this file)

---

## 🚀 Getting Started

### Prerequisites

- Python 3.6+
- Internet connection for stock data retrieval

### Installation

```bash
# Clone repository (if applicable)
git clone https://github.com/yourusername/stock-price-prediction.git
cd stock-price-prediction

# Install dependencies
pip install -r requirements.txt
```

### Usage

```bash
python stock_price_prediction.py
```

Follow the interactive prompts:
1. Enter stock ticker symbol (e.g., `AAPL`, `MSFT`, `GOOGL`)
2. Specify historical data period (e.g., `1y`, `5y`, `max`)
3. Define forecast horizon (number of trading days)

### Output

- Console display of 5 most recent closing prices
- Day-by-day forecast with dates
- Saved visualization as `[TICKER]_prediction_plot.png`

*A chart image will be saved as `[TICKER]_prediction_plot.png` when you run the program*

---

## 💡 Technical Design

### Model Selection Rationale

Random Forest Regressor was chosen for its:
- Superior ability to capture non-linear relationships in financial data
- Robustness against overfitting compared to simpler models
- Excellent performance without extensive hyperparameter tuning
- Capacity to handle feature interactions naturally

### Feature Engineering Approach

The adaptive technical indicator system automatically adjusts calculation parameters based on available data, ensuring optimal feature extraction regardless of the selected time period.

**Core Features:**
- Trend indicators (moving averages)
- Momentum indicators (returns)
- Volatility measures (standard deviation)
- Relative indicators (differences between MAs)

---

## ⚠️ Limitations & Considerations

- **Not Financial Advice**: This tool is designed for educational purposes and should not be used for actual investment decisions
- **Model Constraints**: The Random Forest model does not explicitly account for all time-series dependencies
- **Feature Scope**: Current implementation excludes fundamental data, market sentiment, and macroeconomic factors
- **Forecast Horizon**: Prediction accuracy typically decreases as the forecast horizon extends

---

## 🔮 Future Development

- Enhanced feature set including volume analysis, sentiment data, and macroeconomic indicators
- Implementation of alternative models (LSTM networks, Prophet, XGBoost)
- Hyperparameter optimization framework
- Comprehensive backtesting system
- Web-based user interface
- Portfolio-level analysis and optimization

---

## 💻 Development

### Running Tests

```bash
pytest test_stock_price_prediction.py -v
```

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

*Developed as an educational project for applying machine learning to financial data analysis.*
