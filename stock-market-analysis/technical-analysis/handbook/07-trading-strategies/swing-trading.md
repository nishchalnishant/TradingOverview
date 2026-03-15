# Swing Trading Strategies

## Concept

**Swing trading** holds positions for **several days to weeks**, capturing “swings” within a trend or between support and resistance. It uses **structure** (HH/HL, LH/LL), **key levels**, and **candlestick or chart patterns** for entry and exit. Less time-intensive than scalping; more active than position trading.

---

## Setup Conditions

- **Timeframe:** Typically **4H, daily** for structure and levels; sometimes **1H** for entry refinement. Higher timeframe (e.g. weekly) for **bias** (only long when weekly is bullish).
- **Trend or range:** In **trend,** look for pullbacks to structure (HL, EMA, trendline) or BOS. In **range,** look for support/resistance bounces or breakouts.
- **Pattern (optional):** Chart pattern (flag, triangle) or candlestick pattern (engulfing at level) for clearer entry.

---

## Entry Criteria

- **Pullback in trend:** In uptrend, price pulls back to 20 EMA or 50 EMA or prior HL; **bullish** candle or pattern (hammer, engulfing). Enter on break of the candle high or on next open. Reverse for downtrend.
- **At support/resistance:** Price at clear support (long) or resistance (short); confirmation candle. Enter on break of confirmation candle.
- **Breakout:** Break of range or pattern (e.g. flag) with **close** beyond level and preferably **volume**. Enter on close or on retest.
- **Confirmation:** Prefer **close** beyond a level or **close** of candle in your direction; reduces false signals vs 1m scalping.

---

## Exit Criteria

- **Stop loss:** Below the **swing low** that defined the setup (long), or above the **swing high** (short). Or below/above the pattern (e.g. below flag for long). Place slightly beyond to allow wicks.
- **Take profit:** (1) **Next structure** (next resistance for long, support for short). (2) **Fixed R:R** (e.g. 1:2 or 1:3). (3) **Trailing:** Trail stop under successive swing lows (long); exit when price breaks the trail (e.g. makes a lower low).
- **Time:** Some swing traders exit after N days if target not hit (e.g. 5–10 days) to avoid dead capital.

---

## Stop Loss Placement

- **Structure-based:** Stop where the **thesis is wrong**—e.g. below the HL in an uptrend long. Not arbitrary; use the chart.
- **Buffer:** Small buffer beyond the level (e.g. 0.5% or ATR-based) to avoid normal noise. Or use “close below/above” as invalidation.

---

## Risk:Reward Analysis

- **Target R:R:** **1:2** or **1:3** common; swing trades have room to let winners run. Risk 1% per trade; target 2–3%.
- **Position size:** Risk% = (Entry − Stop) × Size / Account. Solve for size. With wider stops (multi-day), size will be smaller for same % risk.

---

## Backtesting Suggestions

- **Data:** Daily or 4H; several years to capture different regimes (trending vs ranging).
- **Rules:** Define “pullback” (e.g. touch of 20 EMA), “confirmation” (e.g. bullish engulfing), “stop” (e.g. below pullback low). Test on multiple symbols.
- **Metrics:** Win rate, average R, max drawdown, number of trades per year. Swing trading may yield 20–100 trades per year per symbol depending on rules.
- **Walk-forward:** Optimize on rolling window; test on out-of-sample period.

---

*See also: [02 — Trend and Structure](../02-price-action/trend-and-structure.md) | [04 — Chart Patterns](../04-chart-patterns/README.md) | [08 — Risk Management](../08-risk-management/README.md)*
