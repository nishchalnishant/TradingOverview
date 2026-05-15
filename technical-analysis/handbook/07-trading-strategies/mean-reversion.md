# Mean Reversion Strategies

## Concept

**Mean reversion** assumes price will **return** toward an average or a key level (support/resistance) after an **extreme** move. You **fade** the move—buy oversold, sell overbought—rather than follow the trend. Best in **ranging** or **choppy** markets; dangerous in strong trends.

---

## Setup Conditions

- **Range or sideways market:** No clear HH/HL or LH/LL; price oscillates between levels. Or: strong trend but you’re fading a **short-term** overextension (e.g. pullback to VWAP in an uptrend).
- **Extreme identified:** Price at **support** (for longs) or **resistance** (for shorts). Optional: **Oscillator** in overbought (>70 RSI) or oversold (<30 RSI), or price at **Bollinger Band** extreme.
- **Context:** Mean reversion is stronger when the **level** is clear (prior support/resistance, VWAP, round number) and when the **timeframe** is range-bound.

---

## Entry Criteria

- **At support (long):** Price touches support (or dips slightly below then closes back above). Optional: RSI < 30 or Stochastic oversold. **Confirmation:** Bullish candle (hammer, engulfing) or next candle closes higher. Enter on break above confirmation candle high.
- **At resistance (short):** Price touches resistance; optional RSI > 70 or Stochastic overbought. **Confirmation:** Bearish candle. Enter on break below confirmation candle low.
- **Avoid:** Fading in a **strong trend** without a clear level (e.g. shorting just because RSI is 80 in a strong uptrend can be costly). Prefer fading at **structure** (support/resistance).

---

## Exit Criteria

- **Stop loss:** **Below** support for longs (or below the extreme wick); **above** resistance for shorts. If price breaks the level clearly, the mean reversion thesis is wrong—exit.
- **Take profit:** (1) **Opposite side of range** (e.g. resistance for a long from support). (2) **Fixed R:R** (e.g. 1:1 or 1:1.5—mean reversion often uses tighter targets). (3) **Indicator** (e.g. RSI back to 50, or middle Bollinger Band).
- **Time:** If price doesn’t revert within N bars, consider exiting (ranging markets can become trending).

---

## Stop Loss Placement

- **Beyond the level:** Stop below the support low (long) or above the resistance high (short). Use a small buffer for wicks.
- **Risk:** Mean reversion often uses **tighter** stops (level is clear), so position size can be slightly larger for the same % risk—but only if the level is well defined.

---

## Risk:Reward Analysis

- **Typical R:R:** 1:1 or 1:1.5 (target = opposite side of range or midpoint). Win rate can be **higher** (55–65%) than trend following, but winners are smaller. Expectancy = (Win rate × Avg win) − (Loss rate × Avg loss) must be positive.
- **Position size:** Same formula: Risk% = (Entry − Stop) × Size / Account. Size so that one loss doesn’t exceed your risk per trade.

---

## Backtesting Suggestions

- **Regime:** Test only in **ranging** periods (e.g. ADX < 20, or filter by range definition). Mean reversion often loses in strong trends.
- **Levels:** Define support/resistance (e.g. swing high/low, or VWAP). Entry when price within X% of level and RSI oversold/overbought. Measure win rate and average R.
- **Optimization:** Test RSI thresholds (e.g. 25 vs 30 for oversold); stop distance (tight vs beyond level). Avoid overfitting—use out-of-sample test.

---

*See also: [02 — Range vs Trend](../02-price-action/range-vs-trend.md) | [05 — Momentum Indicators](../05-technical-indicators/momentum-indicators.md)*
