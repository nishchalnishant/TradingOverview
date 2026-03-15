# Walk-Forward and Forward Testing

## Walk-Forward Testing

- **Concept:** Split history into **windows**. In each window: **optimize** (or fit) the strategy on the first part (**in-sample**), then **test** on the next part (**out-of-sample**). Roll the window forward and repeat. This checks whether the strategy **holds up** on data it wasn’t tuned on.
- **Example:** Data 2010–2020. Window 1: Optimize on 2010–2014, test on 2015. Window 2: Optimize on 2011–2015, test on 2016. … Aggregate the out-of-sample results.
- **Why:** Reduces **overfitting**. If the strategy only works in-sample but fails out-of-sample, you find out before going live.
- **Caution:** Too many **optimization windows** or **parameters** can still overfit. Keep the strategy simple; use walk-forward as a **sanity check**, not as a way to squeeze more from the same data.

---

## Forward Testing (Paper / Live Small Size)

- **Concept:** After backtest (and optionally walk-forward), run the strategy in **real time** with **paper** trades or **small** real size. No more historical data—you’re testing on **future** data as it comes.
- **Why:** Execution, slippage, and psychology are **different** live. Forward testing reveals if the strategy is **tradeable** (e.g. can you actually get the fills? Do you follow the rules when real money is at stake?).
- **Duration:** Run for at least **1–3 months** or **30–100+** trades (depending on strategy frequency) before judging. One week is usually too short.
- **Compare:** Forward-test results should be **in the same ballpark** as backtest (e.g. similar win rate, positive expectancy). If forward test is much worse, investigate (execution? rule breaks? regime change?).

---

## Trading Psychology

- **Don’t skip forward testing:** A strategy that’s “great” in backtest can fail in live trading. Forward test is the **final** filter.
- **Don’t over-optimize in forward test:** If forward test is weak, avoid the urge to **retune** the strategy to the last month’s data. That’s overfitting to the “forward” period. Instead, refine **general** rules (e.g. add a filter) and test again on **new** forward period.

---

*See also: [Backtesting Basics](backtesting-basics.md) | [Overfitting and Robustness](overfitting-and-robustness.md)*
