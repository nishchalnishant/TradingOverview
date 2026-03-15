# Volume Indicators

Volume indicators incorporate **trading volume** to confirm moves, spot accumulation/distribution, and find high-interest price levels. Volume confirms **strength** of breakouts and reversals.

---

## Volume Profile

- **Concept:** Histogram of **volume at price** (not time). For each price level, sum volume traded at that price. Shows **where** most trading occurred (high volume = important level; often support/resistance or fair value).
- **How used:** **POC (Point of Control):** Price with highest volume; often magnet and support/resistance. **Value Area (VA):** Range that contains a set % of volume (e.g. 70%); price tends to revert to value. **Low-volume nodes (LVN):** Price can move quickly through them; **high-volume nodes (HVN):** Price may pause or reverse. Used for targets and invalidation.
- **Strengths:** Shows meaningful price levels; not just time-based. **Weaknesses:** Calculation depends on period (session, week, etc.); requires volume data.
- **Best conditions:** Any market with reliable volume; intraday and swing for finding key levels.

---

## OBV (On-Balance Volume)

- **Formula:** If Close > Previous Close, OBV += Volume. If Close < Previous Close, OBV −= Volume. If equal, OBV unchanged. Cumulative.
- **How used:** **Trend:** OBV rising = volume supporting upside; OBV falling = volume supporting downside. **Divergence:** Price makes higher high but OBV makes lower high = bearish (buying drying up). Price makes lower low, OBV makes higher low = bullish (selling drying up).
- **Strengths:** Simple; confirms trend and warns of divergence. **Weaknesses:** Cumulative so old data weighs; no absolute level (only trend and divergence matter).
- **Best conditions:** Trend confirmation; divergence at potential reversals.

---

## Accumulation/Distribution (A/D Line)

- **Concept:** Volume-weighted measure of where price closed within the bar’s range. **Money Flow Multiplier** = ((Close − Low) − (High − Close)) / (High − Low). **Money Flow Volume** = MF Multiplier × Volume. A/D = cumulative sum.
- **How used:** Similar to OBV—rising A/D = accumulation (buying pressure); falling = distribution (selling pressure). Divergence with price (e.g. price up, A/D down = weak rally).
- **Strengths:** Weights volume by where price closed in the range. **Weaknesses:** Still cumulative; no absolute level.
- **Best conditions:** Confirm strength of moves; divergence.

---

## VWAP Anchored

- **Concept:** Same as VWAP but **anchored** to a chosen bar (e.g. swing low, high, session open, or a specific date). Doesn’t reset every day unless you choose daily anchor.
- **How used:** Key level for the move from that anchor; institutional level for that “leg.” Entry/exit and target reference. Useful on higher timeframes (e.g. anchor at weekly low).
- **Strengths:** Single important level for a chosen starting point. **Weaknesses:** Subjective anchor choice; not all platforms support it.
- **Best conditions:** Swing and position trading; identifying “fair value” for a move from a specific event or level.

---

## Summary

| Indicator | Measures | Main use |
|-----------|----------|----------|
| Volume Profile | Volume at price | POC, value area, HVN/LVN |
| OBV | Cumulative volume direction | Trend and divergence |
| A/D Line | Volume × close position in range | Accumulation/distribution, divergence |
| VWAP Anchored | VWAP from custom start | Key level for a specific move |

---

*See also: [Trend Indicators](trend-indicators.md) (VWAP) | [01 — Liquidity and Order Flow](../01-market-basics/liquidity-and-order-flow.md)*
