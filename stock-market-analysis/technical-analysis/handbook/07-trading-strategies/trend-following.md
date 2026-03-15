# Trend Following Strategies

## Concept

**Trend following** means trading **in the direction** of the prevailing trend. The edge comes from catching **pullbacks** or **break of structure** in an established trend, not from predicting reversals. “The trend is your friend.”

---

## Setup Conditions

- **Trend identified:** Clear **HH/HL** (uptrend) or **LH/LL** (downtrend) on your trading timeframe. Optional: higher timeframe in same direction (e.g. daily uptrend, 4H pullback).
- **Structure:** In uptrend, look for **pullbacks to** prior HL, trendline, or key MA (e.g. 20 EMA, 50 EMA). In downtrend, pullbacks to prior LH or MA.
- **Filter:** Optional—e.g. price above 200 MA for longs; or ADX > 25 for “trending” regime.

---

## Entry Criteria

- **Pullback entry:** Price pulls back to structure (HL, trendline, EMA) and shows **rejection** (e.g. bullish candle, hammer, engulfing). Enter on break of the rejection candle high (long) or low (short).
- **Break of structure (BOS) entry:** After pullback, price breaks **above** last HH (long) or **below** last LL (short). Enter on the break or on retest of the broken level.
- **Confirmation:** Volume increase on the entry candle; or candle **closes** in your direction (e.g. strong bullish close at support).

---

## Exit Criteria

- **Stop loss:** Below the last **HL** (long) or above the last **LH** (short). Or below the pullback low (long) / above the pullback high (short). Place slightly beyond structure to allow for wicks.
- **Take profit:** (1) **Fixed R:R** (e.g. 1:2 or 1:3). (2) **Structure-based:** Next resistance (long) or support (short). (3) **Trailing:** Trail stop under successive HLs (long) or over LHs (short); exit when structure breaks.
- **Invalidation:** Trend invalidated when structure breaks (e.g. lower low in an uptrend); exit or reduce.

---

## Stop Loss Placement

- **Logical level:** Stop where the **setup is wrong**—e.g. below the swing low that defined the pullback (long). Not an arbitrary number.
- **Buffer:** Add a small buffer (e.g. 0.1% or a few ticks) beyond the level to avoid stop hunts; or use “close below level” as invalidation.

---

## Risk:Reward Analysis

- **Minimum R:R:** Aim for at least **1:1.5** or **1:2** (risk 1 unit to make 1.5–2). Trend following often uses **wider targets** (1:2 or 1:3) because trends can extend.
- **Position size:** Risk per trade (e.g. 1% of account) = (Entry − Stop) × Size. Solve for size.

---

## Backtesting Suggestions

- **Data:** Use multiple instruments and long history (several years) so you see different trend regimes.
- **Metrics:** Win rate, average R per trade, max drawdown, profit factor. Trend following often has **lower win rate** (40–50%) but **positive expectancy** from large winners.
- **Test:** Entry on pullback to EMA 20 in an HH/HL uptrend; stop below pullback low; target 2× risk. Vary parameters (EMA period, R:R) and check robustness.
- **Walk-forward:** Optimize on in-sample period; test on out-of-sample; avoid overfitting.

---

*See also: [02 — Trend and Structure](../02-price-action/trend-and-structure.md) | [08 — Risk Management](../08-risk-management/README.md)*
