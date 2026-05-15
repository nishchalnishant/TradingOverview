# Breakout Strategies

## Concept

**Breakout** strategies enter when price **leaves** a defined range—e.g. horizontal support/resistance, chart pattern (triangle, flag), or consolidation. The idea is to capture the **expansion** that often follows contraction. Breakouts can be **continuation** (in trend) or **reversal** (from a range).

---

## Setup Conditions

- **Range or pattern:** Identify a **clear** range (support and resistance), or a pattern (ascending triangle, flag, rectangle) with a **defined breakout level**.
- **Consolidation:** Price has been contained for a number of bars; volatility may be declining (e.g. Bollinger squeeze, narrow range).
- **Bias (optional):** In a trend, prefer breakouts **in the direction** of the trend (continuation). In a range, breakout direction is the signal.

---

## Entry Criteria

- **Breakout level:** Define the level (e.g. resistance high of range). Enter when price **breaks** that level.
- **Confirmation:** (1) **Close beyond** the level (not just a wick). (2) **Volume** above average on the breakout bar. (3) Optional: **Retest**—wait for price to pull back to the broken level (now support/resistance) and hold, then enter.
- **Avoid:** Chasing far above the level; entering on the first tick (can be a fakeout). Prefer **close** or **retest** to reduce false breakouts.

---

## Exit Criteria

- **Stop loss:** **Below** the breakout level for a long (e.g. below the range or pattern low). **Above** the breakout level for a short. Or below/above the **retest** low/high if you entered on retest.
- **Take profit:** (1) **Measured move:** Height of range/pattern projected from breakout. (2) **Fixed R:R** (e.g. 1:2). (3) **Next structure** (resistance for long, support for short). Consider taking partial profit at first target and trailing the rest.
- **Invalidation:** If price **closes back inside** the range/pattern, treat as failed breakout; exit or tighten stop.

---

## Stop Loss Placement

- **Logical:** Stop on the **other side** of the range/pattern so that a return inside invalidates the trade. For longs: stop below range low (or below retest). For shorts: stop above range high (or above retest).
- **Buffer:** Slight buffer inside the range to allow for wicks; or use “close back inside” as exit rule.

---

## Risk:Reward Analysis

- **Measured move:** If range height is H, target = breakout level ± H. Ensures **R:R ≥ 1:1** if stop is the opposite side of the range.
- **Minimum R:R:** Aim for at least **1:1.5**; many breakouts use **1:2** because false breakouts are common and you want winners to compensate.

---

## Backtesting Suggestions

- **Define breakout:** e.g. “Close above 20-bar high” or “Close above triangle resistance.” Test with and without volume filter.
- **Test:** Different range lengths (e.g. 10-bar, 20-bar range); different confirmation rules (close only vs close + volume). Measure win rate and average R on winning vs losing trades.
- **False breakouts:** Track how often price breaks then closes back inside; optimize entry (e.g. require retest) to improve R:R and reduce whipsaws.

---

*See also: [04 — Chart Patterns](../04-chart-patterns/README.md) | [02 — Range vs Trend](../02-price-action/range-vs-trend.md)*
