# Trend Indicators

Trend indicators **smooth price** or **define trend direction** to help identify the prevailing trend and potential support/resistance. They work best in **trending** markets and can whipsaw in **ranges**.

---

## Moving Average (MA)

- **Concept:** Average of price over N periods. **Simple MA (SMA)** = arithmetic mean; **Exponential MA (EMA)** gives more weight to recent prices.
- **SMA formula:** SMA = (P₁ + P₂ + … + Pₙ) / N (usually close price).
- **EMA formula:** EMA_today = α × Price_today + (1 − α) × EMA_yesterday, where α = 2 / (N + 1).

| Type | Weighting | Use |
|------|-----------|-----|
| **SMA** | Equal weight all periods | Longer-term trend; less reactive |
| **EMA** | More weight to recent | Faster reaction; popular for 9, 20, 50, 200 |

- **How used:** Price above MA = bullish bias; below = bearish. Crossovers (e.g. fast EMA above slow EMA = bullish). MAs as dynamic support/resistance.
- **Strengths:** Simple, visual, good for trend filter. **Weaknesses:** Lagging; choppy in sideways markets.
- **Best conditions:** Trending markets; higher timeframes for fewer false signals.

---

## VWAP (Volume-Weighted Average Price)

- **Concept:** Average price weighted by **volume**. Usually calculated from the **session open** (e.g. daily open) so it resets each session.
- **Formula:** VWAP = Σ(Price × Volume) / Σ(Volume) from session start to current bar.
- **How used:** Price above VWAP = bullish intraday bias; below = bearish. Institutions often use VWAP as benchmark; pullbacks to VWAP as entries. Used for mean reversion or trend confirmation.
- **Strengths:** Incorporates volume; single clear level per session. **Weaknesses:** Resets each session; not useful on higher timeframes without “anchored” variant.
- **Best conditions:** Intraday (e.g. equities, futures); liquid markets.

---

## Ichimoku Cloud (Ichimoku Kinko Hyo)

- **Components:**
  - **Tenkan-sen (Conversion):** (9-period high + 9-period low) / 2.
  - **Kijun-sen (Base):** (26-period high + 26-period low) / 2.
  - **Senkou Span A (Leading A):** (Tenkan + Kijun) / 2, shifted 26 periods forward.
  - **Senkou Span B (Leading B):** (52-period high + 52-period low) / 2, shifted 26 periods forward.
  - **Chikou Span (Lagging):** Close shifted 26 periods back.
- **Cloud (Kumo):** Area between Senkou A and Senkou B. Price above cloud = bullish; below = bearish. Cloud acts as support/resistance.
- **How used:** Trend = price vs cloud. Entry: pullback to Kijun or cloud in trend direction. Chikou Span: if current price is above Chikou, bullish confirmation.
- **Strengths:** Multiple inputs in one system; visual. **Weaknesses:** Complex; many parameters; lagging.
- **Best conditions:** Trending markets; medium-to-higher timeframes.

---

## Parabolic SAR (Stop and Reverse)

- **Concept:** Dots that sit **below** price in an uptrend and **above** price in a downtrend. They **trail** price and act as a trailing stop. When price crosses the dots, the indicator “flips” to the other side (trend reversal signal).
- **Formula:** SAR moves toward price each period; acceleration factor increases until a new extreme is made. (Exact formula is iterative.)
- **How used:** Dots below = bullish; trade pullbacks to the line. Dots above = bearish. Cross of price through SAR = potential trend change (often used as exit or reverse).
- **Strengths:** Clear trailing stop; good in strong trends. **Weaknesses:** Very poor in choppy markets; many false flips.
- **Best conditions:** Strong, smooth trends; avoid in tight ranges.

---

## Summary

| Indicator | Measures | Best for |
|-----------|----------|----------|
| SMA/EMA | Smoothed price, direction | Trend filter, dynamic S/R |
| VWAP | Volume-weighted average | Intraday bias, institutional level |
| Ichimoku | Trend, momentum, S/R | Multi-factor trend system |
| Parabolic SAR | Trailing stop, trend flip | Strong trends only |

---

*See also: [Momentum Indicators](momentum-indicators.md) | [02 — Dynamic S/R and Trendlines](../02-price-action/dynamic-support-resistance-trendlines.md)*
