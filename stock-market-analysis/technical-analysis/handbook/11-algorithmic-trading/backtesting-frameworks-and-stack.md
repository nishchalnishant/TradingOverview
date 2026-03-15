# Backtesting Frameworks and Basic Python Trading Stack

## Basic Python Trading Stack

A minimal stack for **research and backtesting**:

- **Python 3.x** (e.g. 3.9+).
- **pandas:** DataFrames for OHLCV; easy indexing and calculations.
- **numpy:** Numerical operations; used by pandas and many indicators.
- **Data source:** yfinance, pandas-datareader, or broker/data API to load history.
- **Backtesting:** Either **custom** (loop over bars, track positions, apply rules) or a **library** (see below).
- **Visualization (optional):** matplotlib, plotly for equity curve and charts.

For **live** trading add: **broker API** client, **scheduler** (e.g. run every 1m) or **WebSocket** for real-time, **logging** and **error handling**.

---

## Backtesting Frameworks (Python)

| Framework | Style | Pros | Cons |
|-----------|--------|------|------|
| **backtrader** | Event-driven | Flexible; indicators; multiple data feeds | Steeper learning curve |
| **vectorbt** | Vectorized | Fast; many symbols; parameter scans | Less intuitive for complex logic |
| **zipline** | Event-driven | Used by Quantopian legacy; pipeline | Less maintained |
| **Custom loop** | Your code | Full control; no black box | More work; you handle everything |

**Recommendation:** Start with **custom loop** (pandas + simple for-loop over bars) to understand fills and P&L. Then try **backtrader** or **vectorbt** if you need more structure or speed.

---

## Data Sources (Summary)

- **Free:** yfinance (Yahoo), Alpha Vantage (with key), FRED (macro). Good for **learning** and **equity** history.
- **Paid:** Polygon, Quandl, Refinitiv. Better **quality**, **depth**, and **latency** for serious backtesting and live.
- **Crypto:** Exchange APIs (Binance, etc.) or aggregators (e.g. CryptoCompare). Check **history** length and **rate limits**.

---

## Example Workflow

1. **Fetch data:** `yfinance.download("SPY", start="2020-01-01")` → DataFrame.
2. **Compute indicators:** e.g. SMA(20), RSI(14) with pandas/numpy or ta-lib.
3. **Signals:** e.g. long when close > SMA and RSI > 30 and RSI was < 30 previous bar.
4. **Simulate:** For each bar, if signal and no position → enter; if exit condition → exit. Record entry/exit price, P&L. Apply commission.
5. **Metrics:** Win rate, expectancy, max drawdown from trade list.
6. **Plot:** Equity curve (cumulative P&L over time).

---

*See also: [10 — Backtesting](../10-backtesting/README.md) | [APIs and Data](apis-and-data.md)*
