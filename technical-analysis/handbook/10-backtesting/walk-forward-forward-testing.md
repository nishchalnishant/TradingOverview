# Walk-Forward and Forward Testing

## Walk-Forward Testing

**Walk-forward testing** applies optimization and validation in rolling windows across historical data. Rather than fitting a strategy once on all history and declaring it done, you repeatedly optimize on a sub-period ("in-sample") and immediately test on the next untouched sub-period ("out-of-sample"), then slide the window forward and repeat.

### Why It Matters

A standard backtest lets the optimizer see all the data, which makes it easy to find parameters that worked historically but may not generalize. Walk-forward forces out-of-sample validation at every step, giving a realistic estimate of how the strategy would have performed if you had deployed it live at each point in history.

---

## Window Types

### Rolling (Anchored-End) Walk-Forward

Each optimization window has the **same fixed length** and slides forward in time:

```
IS = In-Sample (optimize)   OOS = Out-of-Sample (validate)

Window 1:  [2010–2013 IS] → [2014 OOS]
Window 2:  [2011–2014 IS] → [2015 OOS]
Window 3:  [2012–2015 IS] → [2016 OOS]
...
```

- IS and OOS lengths stay constant.
- Assumes recent history is more predictive than older history.
- Typical IS:OOS ratio: **3:1 to 5:1** (e.g. 12 months IS, 3 months OOS).

### Anchored (Expanding) Walk-Forward

The IS window always starts at the **same origin** and grows:

```
Window 1:  [2010–2013 IS] → [2014 OOS]
Window 2:  [2010–2014 IS] → [2015 OOS]
Window 3:  [2010–2015 IS] → [2016 OOS]
...
```

- Useful when all history is considered relevant (e.g. broad regime data).
- Risk: early, less-relevant data can dilute recent patterns.

### Choosing Window Sizes

| Consideration | Guideline |
|---|---|
| OOS must contain enough trades | At least 30 trades per OOS window for statistical significance |
| IS:OOS ratio | 3:1 to 5:1 is common; shorter OOS = more windows but noisy |
| Total OOS coverage | Aim for OOS periods to cover at least 2–3 full market cycles |
| Strategy frequency | Intraday: weeks/months per window; swing: months/years |

---

## Walk-Forward Efficiency Ratio (WFE)

The **Walk-Forward Efficiency Ratio** compares the aggregate OOS performance to the IS performance:

```
WFE = (Net Profit OOS / Net Profit IS)  ×  (IS length / OOS length)
```

Or more simply, the ratio of **annualized OOS return** to **annualized IS return**:

```
WFE = Annualized OOS Return ÷ Annualized IS Return
```

| WFE Range | Interpretation |
|---|---|
| > 0.7 | Strong: OOS performs close to IS; low overfitting |
| 0.5 – 0.7 | Acceptable: some decay but strategy generalizes |
| 0.3 – 0.5 | Weak: significant OOS deterioration; suspect overfitting or regime sensitivity |
| < 0.3 | Poor: strategy likely overfitted or fragile; do not trade |
| Negative | OOS is unprofitable while IS was; strategy is curve-fitted or data-mined |

A WFE above 0.5 combined with **consistent OOS profitability** across most windows is a reliable minimum bar before considering live deployment.

---

## Evaluating Out-of-Sample Results

Do not judge OOS performance on net profit alone. Examine:

| Metric | What to Look For |
|---|---|
| Win rate (OOS vs IS) | Should not drop dramatically (>10–15 pp decline is a warning) |
| Expectancy | Positive OOS expectancy is non-negotiable |
| Maximum drawdown | OOS drawdown should not far exceed IS drawdown |
| Profit factor | OOS profit factor > 1.3 is a reasonable threshold |
| # of OOS windows profitable | At least 60–70% of windows should be positive |
| Sharpe/Sortino | Risk-adjusted OOS return should be positive |

A strategy where most OOS windows are profitable but a few large losses drag down aggregate numbers may still be viable — investigate *why* those windows failed (regime change? specific market event?) before discarding.

---

## Diagnosing a Failing Walk-Forward

### Consistently Poor OOS Across All Windows
- The strategy is likely **overfitted** to IS structure that doesn't generalize.
- Reduce the number of free parameters; simplify entry and exit rules.
- Run a Monte Carlo permutation test: if randomized data produces similar OOS results, there is no genuine edge.

### OOS Profitable in Some Periods, Not Others
- Strategy may be **regime-dependent**: works in trending markets, fails in ranges (or vice versa).
- Add a **regime filter** (e.g. ADX > 25 for trend strategies) and retest.
- Consider whether the failing OOS windows correspond to identifiable market conditions.

### OOS Sharply Worse Than IS but Still Profitable
- Moderate overfitting. WFE in the 0.4–0.6 range.
- Acceptable if absolute OOS metrics are strong. Reduce IS optimization depth; use fewer parameter combinations.

### Parameter Instability
- Best IS parameters change dramatically window to window (e.g. fast MA = 5 in window 1, 20 in window 2).
- This signals **fragility**: the strategy has no robust parameter region.
- Fix: test parameter robustness by checking if a neighborhood of values around the optimum also performs well ("robustness plateau").

---

## Forward Testing Protocol

### What It Is

After a strategy passes backtesting and walk-forward, **forward testing** (paper trading or live at minimum size) is the final validation stage. You are now testing on genuinely unseen data — the future.

### Minimum Sample Requirements

| Strategy Type | Minimum Trade Count | Suggested Duration |
|---|---|---|
| High-frequency / scalping | 200–500 trades | 2–4 weeks |
| Intraday (10–20 trades/day) | 100–200 trades | 1–2 months |
| Swing (3–10 trades/week) | 50–100 trades | 2–4 months |
| Position (1–5 trades/month) | 30–60 trades | 6–12 months |

One or two weeks is **never** enough regardless of strategy type. You need enough trades for the law of large numbers to reveal the true expectancy.

### What to Track During Forward Testing

1. **Every trade**: entry, exit, size, reason, P&L.
2. **Slippage**: difference between signal price and actual fill price. Compare to backtest assumptions.
3. **Rule adherence**: did you (or the algorithm) follow all rules exactly?
4. **Metric comparison**: rolling win rate, average R, max drawdown vs backtest expectations.

### Interpreting Forward Test Results

| Forward vs Backtest | Interpretation |
|---|---|
| Within 20% of key metrics | Strategy is behaving as expected; continue to full size on schedule |
| 20–40% degradation | Investigate: execution differences? Rule breaks? Regime change? Do not scale up yet |
| > 40% degradation or negative expectancy | Stop. Do not add size. Re-examine the strategy from scratch |

### Diagnosing a Failing Forward Test

1. **Execution gap**: Fills worse than assumed? Add realistic slippage to backtest and re-evaluate.
2. **Rule breaks**: Were all trades taken per the rules? If not, the forward test is of you, not the strategy.
3. **Regime change**: Is the market behaving differently now than in the backtest period? Check volatility regime, trend character, correlation structure.
4. **Look-ahead or data artifacts in backtest**: If the strategy looked perfect in backtest but fails live, suspect a coding error (look-ahead bias, survivorship bias in the data, incorrect bar indexing).
5. **Sample too small**: Reserve judgment until minimum trade count is reached. One losing month is not conclusive.

---

## Key Rules

- Never retune parameters during the forward test period. Changes invalidate the test.
- A failing forward test is **data** — diagnose before discarding or rebuilding the strategy.
- If you must make changes, restart the forward test clock from zero on the revised strategy.
- Walk-forward and forward testing together form a **two-stage filter**: walk-forward catches overfitting on history; forward testing catches execution and regime issues.

---

*See also: [Backtesting Basics](backtesting-basics.md) | [Overfitting and Robustness](overfitting-and-robustness.md) | [Tools: Python and TradingView](tools-python-tradingview.md)*
