# AlgoTrading-on-Kite  
**Algorithmic Trading Using Price Action and Zerodha Kite API**

This project presents an algorithmic trading system built using **price action principles**, **candlestick analysis**, and **support-resistance detection**. The system integrates with the **Zerodha Kite API** for real-time data retrieval and automated trade execution.

---

## 1. Overview

The project aims to automate trade decisions by combining price action strategies with algorithmic logic.  
It focuses on:
- Detecting support and resistance levels  
- Identifying key candlestick patterns (bullish and bearish)  
- Automating buy/sell signal generation  
- Executing trades through Zerodha’s Kite API  
- Applying risk management techniques such as stop loss and trailing profit

---

## 2. Features

### Price Action and Technical Analysis
- Dynamic identification of support and resistance zones  
- Candlestick pattern recognition:
  - Bullish Engulfing and Hammer (Buy signals)
  - Bearish Engulfing and Shooting Star (Sell signals)
- Signal validation based on price proximity to key levels

### Automated Workflow
- Web scraping for real-time OHLC data (via Selenium)
- Data cleaning and transformation using Pandas
- Integration with Kite Connect API for order execution
- LSTM-based price prediction module for signal validation (optional)

### Risk Management
- Automated stop-loss and trailing stop-loss logic  
- Profit booking thresholds  
- Trade logging and performance tracking

---

## 3. Project Structure

```
AlgoTrading-on-Kite/
│
├── Fundamentals/             # Basic notebooks on Kite API and indicator concepts
├── MACD/                     # MACD indicator implementation
├── SuperTrend/               # SuperTrend indicator logic
├── Price Action Strategy/    # Price action signal generation
├── Trading_Strategy/         # Combined trading systems
└── Final Project/            # End-to-end implementation notebook
    └── final.ipynb
```

---

## 4. Installation and Setup

### Step 1: Clone the repository
```bash
git clone https://github.com/jayasuryan-mutyala/AlgoTrading-on-Kite.git
cd "Final Project"
```

### Step 2: Install dependencies
```bash
pip install -r requirements.txt
```

If `requirements.txt` is not available:
```bash
pip install numpy pandas matplotlib seaborn plotly scikit-learn ta kiteconnect selenium jupyter
```

### Step 3: Launch Jupyter Notebook
```bash
jupyter notebook final.ipynb
```

---

## 5. Configuration

Before executing live or paper trades, set up your Kite API credentials as environment variables:
```bash
export KITE_API_KEY="your_api_key"
export KITE_API_SECRET="your_api_secret"
export KITE_ACCESS_TOKEN="your_access_token"
```

Alternatively, store them securely in a `.env` file (do not commit credentials to version control).

---

## 6. Workflow

1. **Data Collection**  
   Retrieve live or historical market data via Kite API or web scraping.

2. **Feature Engineering**  
   Identify support/resistance zones and relevant candlestick formations.

3. **Signal Generation**  
   - Buy: Bullish Engulfing or Hammer near support  
   - Sell: Bearish Engulfing or Shooting Star near resistance

4. **Trade Execution**  
   Execute trades automatically using Kite Connect API.

5. **Performance Evaluation**  
   Generate trade logs, visualize buy/sell points, and compute profit/loss metrics.

---

## 7. Example Output

The notebook visualizes:
- Buy/Sell markers on price charts  
- Trade summaries with entry, exit, and P&L  
- Model accuracy (if LSTM module is used)  

Example trade log:
```
BUY  | Date: 2025-01-15 | Price: 442.5 | Target: 448.0 | Stop Loss: 439.0
SELL | Date: 2025-01-20 | Price: 455.2 | Target: 449.0 | Stop Loss: 458.5
```

---

## 8. Backtesting and Deployment

| Mode | Description |
|------|--------------|
| **Backtesting** | Simulates strategy on historical data for P&L evaluation |
| **Paper Trading** | Simulates live market conditions without real money |
| **Live Trading** | Executes trades on Zerodha using real credentials |

Before live deployment, extensive paper trading and validation are strongly recommended.

---

## 9. Future Enhancements
- Multi-timeframe confirmation logic (e.g., 15m + 1h)  
- Integration of RSI and EMA crossover indicators  
- Enhanced backtesting engine with slippage and transaction cost modeling  
- Database integration for trade storage and analytics  
- Live monitoring dashboard using Streamlit or Dash

---

## 10. Disclaimer

This project is intended for **educational and research purposes only**.  
Trading in financial markets involves significant risk, including possible loss of capital.  
The author and contributors are **not responsible for any financial loss or misuse** of the provided code.  
Always validate strategies thoroughly before applying in live trading.
