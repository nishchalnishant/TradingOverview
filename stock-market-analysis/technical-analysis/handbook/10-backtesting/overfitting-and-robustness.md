# Overfitting and Robustness

## Overfitting

- **Definition:** Fitting the strategy **too closely** to historical data so that it “memorizes” the past rather than capturing a **general** edge. Result: great backtest, **poor** performance on new data (out-of-sample or live).
- **Causes:** Too many **parameters** (e.g. 10 moving average periods and 5 RSI levels). **Optimizing** until the curve looks perfect. Using **short** or **single-instrument** data. **Curve-fitting** entry/exit rules to specific dates.
- **Signs:** Backtest is **too good** (e.g. 80% win rate, smooth equity curve). Small change in parameters **destroys** performance. Strategy fails in walk-forward or forward test.

---

## How to Reduce Overfitting

1. **Simple rules:** Fewer parameters (e.g. one or two indicators, one or two levels). Simple strategies often **generalize** better.
2. **Out-of-sample test:** Never optimize on the **same** data you use to report performance. Reserve **last 20–30%** of history (or use walk-forward) for testing.
3. **Multiple instruments:** Test on **several** symbols or markets. If it only works on one, it’s likely overfit to that one.
4. **Long history:** Use **many years** of data so that different regimes (trending, ranging, high/low vol) are included.
5. **Sensitivity analysis:** Vary parameters (e.g. SMA 18, 20, 22). If performance **collapses** with small changes, the strategy is fragile.
6. **Economic logic:** Prefer rules that have a **reason** (e.g. “support holds because buyers step in”) over arbitrary numbers (e.g. “exit when RSI = 67.3”).

---

## Robustness

- **Robust strategy:** Performs **reasonably** across different instruments, time periods, and parameter variations. Not “best” in every case, but **positive** expectancy in many.
- **Check:** Run backtest on **different** assets (e.g. indices, forex, commodities). Run on **different** start/end dates. If results are **stable** (e.g. always positive expectancy, similar win rate), the strategy is more trustworthy.

---

## Trading Psychology

- **Accept “good enough”:** A strategy with 55% win rate and 1:1.5 R:R that is **robust** is better than a 70% win rate strategy that only works on one symbol and one period.
- **Don’t chase the perfect backtest:** The goal is **live** performance. Sacrifice some backtest “beauty” for **simplicity** and **stability**.

---

*See also: [Backtesting Basics](backtesting-basics.md) | [Walk-Forward and Forward Testing](walk-forward-forward-testing.md)*
