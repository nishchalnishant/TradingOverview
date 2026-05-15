# Backtesting Strategies: Basics

## Concept

**Backtesting** means running your **trading rules** on **historical price (and volume) data** and recording hypothetical trades: entry, exit, P&L. The result is a **series of trades** and performance metrics (win rate, expectancy, drawdown, profit factor) that estimate how the strategy would have performed.

---

## Steps

1. **Define the strategy:** Clear, unambiguous rules (e.g. “Buy when close > 20 SMA and RSI crosses above 30 from below; stop below prior bar low; target 2× risk”).
2. **Get data:** Sufficient **history** (e.g. 5–10 years for daily; 1–2 years for intraday), **quality** (adjusted for splits/dividends), and **granularity** (e.g. 1m bars for a scalping test).
3. **Implement:** Code or use a platform (TradingView, Python, etc.) to loop through bars, detect signals, and simulate fills.
4. **Assume realistic execution:** Include **spread** and **commission**; optionally **slippage** (e.g. 1 tick). Use **close** or **next open** for fills to avoid look-ahead bias.
5. **Record every trade:** Entry/exit time and price, P&L, drawdown. Compute metrics.

---

## Common Pitfalls

- **Look-ahead bias:** Using information that wouldn’t have been available at the time (e.g. using today’s close to decide today’s entry). Only use **past** data at each bar.
- **Survivorship bias:** Testing only on symbols that exist today (missing delisted, failed companies). Use **point-in-time** universe or survivorship-bias-free data if possible.
- **Overfitting:** Optimizing parameters until backtest is “perfect.” Strategy then fails on new data. Keep **few** parameters; test on **multiple** instruments and **out-of-sample** period.
- **Ignoring costs:** Real trading has spread and commission. A strategy that’s profitable **before** costs can be losing **after**.
- **Unrealistic fills:** Assuming you always get the **exact** high/low for a stop or limit. In reality, you might get worse (slippage). Use conservative fill assumptions.

---

## Metrics to Report

- **Win rate** (%)
- **Average R** (or average win/loss in $)
- **Expectancy** (avg $ or R per trade)
- **Profit factor** (gross profit / gross loss)
- **Max drawdown** ($ and %)
- **Number of trades** (and over how many years)
- **Sharpe ratio** (optional; return per unit of risk)

---

## Trading Psychology

- **Backtest ≠ future:** Past performance doesn’t guarantee future results. Use backtest to **filter** ideas (e.g. negative expectancy = drop it) and **rough** sizing, not as a promise.
- **Forward test:** After a good backtest, run **paper or small-size live** (forward test) before going full size.

---

*See also: [Walk-Forward and Forward Testing](walk-forward-forward-testing.md) | [Overfitting and Robustness](overfitting-and-robustness.md)*
