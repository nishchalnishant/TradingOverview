# Volatility Indicators

Volatility indicators measure **how much price moves** (range or deviation). They help with **position sizing**, **stop placement**, and **breakout** or **squeeze** setups. They do **not** indicate direction—only the size of moves.

---

## Bollinger Bands

- **Components:**  
  - **Middle band:** SMA(Close, N), usually N = 20.  
  - **Upper band:** Middle + k × StdDev(Close, N).  
  - **Lower band:** Middle − k × StdDev(Close, N).  
  Typical k = 2.
- **How used:** Price near **upper band** = strong move up (or overbought in a range). Price near **lower band** = strong move down (or oversold). **Squeeze:** When bands contract, volatility is low; expansion often follows (breakout). **Mean reversion:** Fade touches of the bands in a range; **trend:** Use band touches as pullbacks in a trend (e.g. long on touch of middle or lower band in uptrend).
- **Strengths:** Adapts to volatility; squeeze signals potential breakout. **Weaknesses:** In strong trends price can walk the band; not a standalone direction signal.
- **Best conditions:** Squeeze for breakout; mean reversion in ranges; band as dynamic S/R in trends.

---

## ATR (Average True Range)

- **True Range (TR):** max(High − Low, |High − Previous Close|, |Low − Previous Close|). Captures gaps.
- **ATR:** Average of TR over N periods (e.g. 14). Usually SMA or Wilder’s smoothing.
- **How used:** **Volatility filter:** High ATR = wide stops and targets; low ATR = tighter. **Stop placement:** Stop = entry ± k × ATR (e.g. 1.5–2× ATR). **Target:** Same; e.g. 2× ATR target. **Breakouts:** Expansion from low ATR often precedes a move.
- **Strengths:** Simple; directly useful for risk (stops, targets). **Weaknesses:** No direction; lags.
- **Best conditions:** All markets for **sizing and stops**; low ATR for anticipating expansion.

---

## Keltner Channels

- **Concept:** Similar to Bollinger Bands but the bands are based on **ATR** (or EMA distance) instead of standard deviation. Middle line often EMA.
- **Typical:** Middle = EMA(Close, 20). Upper = Middle + k × ATR(10). Lower = Middle − k × ATR(10). k often 2.
- **How used:** Price outside the channel = strong move. **Squeeze:** Narrow channels suggest low volatility; breakout when price leaves the channel. Can be used for mean reversion (fade channel touches) or trend (hold in trend, channel as dynamic S/R).
- **Strengths:** ATR-based so reflects actual range; less “spiky” than Bollinger in some assets. **Weaknesses:** Still no direction; parameters matter.
- **Best conditions:** Similar to Bollinger—squeeze, mean reversion, or trend pullbacks.

---

## Summary

| Indicator | Measures | Main use |
|-----------|----------|----------|
| Bollinger Bands | Price vs 2 std dev from SMA | Squeeze, mean reversion, dynamic S/R |
| ATR | Average true range | Stops, targets, volatility filter |
| Keltner Channels | Price vs ATR-based bands | Squeeze, breakouts, dynamic S/R |

---

*See also: [Volume Indicators](volume-indicators.md) | [08 — Risk Management (position sizing)](../08-risk-management/README.md)*
