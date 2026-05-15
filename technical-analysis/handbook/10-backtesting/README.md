# Section 10 — Backtesting and Data Analysis

Backtesting is **testing a strategy on historical data** to estimate performance (win rate, expectancy, drawdown) before risking real money. Done well, it helps validate an edge; done poorly, it leads to **overfitting** and false confidence.

---

## Contents

| Document | Topic |
|----------|--------|
| [Backtesting Basics](backtesting-basics.md) | How to backtest; common pitfalls |
| [Walk-Forward and Forward Testing](walk-forward-forward-testing.md) | Out-of-sample and live testing |
| [Overfitting and Robustness](overfitting-and-robustness.md) | Avoiding curve-fitting |
| [Tools: Python and TradingView](tools-python-tradingview.md) | Practical tools for research and backtesting |

---

## Key Ideas

- **Backtest** = run strategy logic on past data; record trades, P&L, drawdown. Use **realistic** assumptions (costs, slippage, liquidity).
- **Walk-forward:** Optimize on one period; test on the **next** period (out-of-sample). Reduces overfitting.
- **Forward testing:** Trade the strategy **live** with small size (or paper) to see if it holds up. Final validation.
- **Overfitting:** Tweaking rules until backtest looks great—but the strategy fails on new data. Keep rules **simple** and **few**; test on **multiple** instruments and **long** history.

---

## Quick Links

- Strategies: [07 — Trading Strategies](../07-trading-strategies/README.md) | Algo: [11 — Algorithmic Trading](../11-algorithmic-trading/README.md)
