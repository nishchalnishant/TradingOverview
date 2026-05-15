# Momentum Indicators

Momentum indicators measure **speed and change** of price (and sometimes volume). They often oscillate between overbought/oversold zones or show **divergence** from price. Useful in both **trends** (confirmation) and **ranges** (overbought/oversold).

---

## RSI (Relative Strength Index)

- **Formula:** RSI = 100 − (100 / (1 + RS)), where RS = average gain / average loss over N periods (usually 14). Smoothed with Wilder’s method (or EMA).
- **Range:** 0–100. Typically **>70** = overbought, **<30** = oversold (context-dependent).
- **How used:** Overbought/oversold in ranges; in trends, RSI can stay overbought (bullish) or oversold (bearish) for long periods. **Divergence:** Price makes higher high but RSI makes lower high = bearish divergence (potential reversal). Price makes lower low, RSI makes higher low = bullish divergence.
- **Strengths:** Simple; divergence can warn of reversals. **Weaknesses:** Lagging; overbought/oversold is misleading in strong trends.
- **Best conditions:** Ranging markets for mean reversion; trends for divergence or “pullback in trend” (e.g. RSI 40–50 in uptrend = healthy pullback).

---

## MACD (Moving Average Convergence Divergence)

- **Components:**  
  - **MACD line:** (EMA_fast − EMA_slow), e.g. 12 and 26.  
  - **Signal line:** EMA of MACD line, e.g. 9.  
  - **Histogram:** MACD − Signal (optional).
- **How used:** **Crossover:** MACD crosses above Signal = bullish; below = bearish. **Zero line:** MACD above zero = short-term above long-term average (bullish). **Divergence:** Price vs MACD (e.g. higher high in price, lower high in MACD = bearish).
- **Strengths:** Trend and momentum in one; crossovers and divergence. **Weaknesses:** Lagging; many false crossovers in chop.
- **Best conditions:** Trending markets; higher timeframes for fewer false signals.

---

## Stochastic Oscillator

- **Formula:** %K = 100 × (Close − Low_n) / (High_n − Low_n). %D = SMA of %K (e.g. 3-period). Typical n = 14.
- **Range:** 0–100. **>80** = overbought, **<20** = oversold.
- **How used:** Overbought/oversold; **crossover** of %K and %D (e.g. %K crosses above %D in oversold = bullish). Divergence with price as with RSI.
- **Strengths:** Sensitive; good for short-term reversals in ranges. **Weaknesses:** Very noisy in strong trends; many false signals.
- **Best conditions:** Ranging or mean-reversion setups; can be used in trends for pullback entries (e.g. stochastic crossing up from oversold in an uptrend).

---

## CCI (Commodity Channel Index)

- **Formula:** CCI = (Price − SMA(Price)) / (0.015 × Mean Deviation). Typical period 20. Unbounded (no fixed 0–100).
- **Typical levels:** **+100** = overbought, **−100** = oversold (can use ±200 for stronger moves).
- **How used:** Similar to RSI/Stochastic for overbought/oversold and divergence. Some use CCI for trend (e.g. CCI > 0 = bullish).
- **Strengths:** Unbounded so can show extreme momentum. **Weaknesses:** Less common; similar pitfalls to other oscillators in trends.
- **Best conditions:** Mean reversion in ranges; divergence in trends.

---

## Momentum Indicator (Rate of Change style)

- **Concept:** Rate of change of price over N periods. e.g. Momentum = Close − Close_n (or (Close / Close_n) × 100).
- **How used:** Positive = upward momentum; negative = downward. Cross of zero can signal trend change. Divergence with price (e.g. price higher high, momentum lower high = warning).
- **Strengths:** Simple; no upper/lower bound. **Weaknesses:** Lagging; no overbought/oversold level unless normalized.
- **Best conditions:** Trend confirmation; divergence.

---

## Summary

| Indicator | Range/Output | Main use |
|-----------|----------------|----------|
| RSI | 0–100 | Overbought/oversold, divergence |
| MACD | Line + Signal + Histogram | Crossovers, zero line, divergence |
| Stochastic | 0–100 | Overbought/oversold, %K/%D cross |
| CCI | Unbounded | Extremes, divergence |
| Momentum | Unbounded | Direction, zero cross, divergence |

---

*See also: [Trend Indicators](trend-indicators.md) | [Volatility Indicators](volatility-indicators.md)*
