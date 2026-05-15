# Using Python and TradingView for Backtesting

## Python for Trading Research

- **Why Python:** Flexible; you can pull **data** (e.g. yfinance, pandas-datareader, broker APIs), **compute** indicators and signals, and **simulate** trades. Full control over logic and assumptions.
- **Typical stack:** **pandas** (data), **numpy** (calculations), **matplotlib/plotly** (charts). For backtesting: **backtrader**, **zipline**, **vectorbt**, or **custom** loop over bars.
- **Data sources:** Free: Yahoo Finance (yfinance), Alpha Vantage, FRED. Paid: Polygon, Quandl, broker data. Ensure **adjustments** (splits, dividends) are applied for equities.
- **Workflow:** (1) Load OHLCV data. (2) Compute indicators (SMA, RSI, etc.). (3) Generate signals (e.g. crossovers, level breaks). (4) Simulate orders (entry/exit), apply costs. (5) Compute P&L, drawdown, metrics. (6) Plot equity curve and analyze.

---

## TradingView for Backtesting

- **Why TradingView:** No coding; **visual** strategy builder or **Pine Script**. Built-in data and charts; many traders already use it.
- **Strategy tab:** Create a strategy (conditions for long/short, exit). Run **strategy backtester** on a symbol and timeframe. Get net profit, win rate, max drawdown, number of trades.
- **Limitations:** (1) **Fills** are often at open/close of bar; may be optimistic. (2) **Costs:** Add spread/commission in settings. (3) **Slippage:** Not always modeled. (4) **Data:** Depends on TradingView’s history; some symbols have limited history.
- **Best for:** Quick **sanity checks** and **visual** idea testing. For rigorous research, Python (or similar) gives more control (realistic fills, custom data, walk-forward).

---

## When to Use Which

- **TradingView:** Fast idea test; visual; no code. Use for **screening** strategies and **learning**.
- **Python:** Reproducible; customizable (costs, slippage, multi-asset, walk-forward). Use for **serious** backtesting and **quant** work.
- **Hybrid:** Develop idea in TradingView; replicate and deepen in Python with proper data and robustness checks.

---

## Backtesting Frameworks (Python)

- **backtrader:** Event-driven; flexible; good for custom logic.
- **vectorbt:** Vectorized; fast; good for many symbols and parameter scans.
- **Custom loop:** For full control (e.g. tick-by-tick, custom order types). More work but no black box.

---

*See also: [11 — Algorithmic Trading](../11-algorithmic-trading/README.md) | [Backtesting Basics](backtesting-basics.md)*
