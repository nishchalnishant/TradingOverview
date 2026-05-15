# Technical Analysis — Detailed Summary

Condensed overview of the Technical Analysis Handbook. For full detail and examples, use the [Handbook](https://github.com/nishchalnishant/TradingOverview/tree/main/stock-market-analysis/technical-analysis/handbook) and [Revision](https://github.com/nishchalnishant/TradingOverview/tree/main/Revision) materials.

---

## 1. Market Basics

- **Markets:** Price discovery via matching of buy/sell orders. Liquidity = ability to trade without moving price much. Order flow imbalance drives short-term moves.
- **Participants:** Retail, institutional, market makers, HFT. Each affects liquidity and volatility.
- **Bid/Ask/Spread:** Bid = best buy price; Ask = best sell price; Spread = cost of round-trip. Slippage = fill worse than quote.
- **Order types:** Market (immediate); Limit (at price or better); Stop (triggers market order at level); Stop-limit (triggers limit at level).
- **Sessions:** Asian, London, NY. London+NY overlap = highest FX volatility. Equities: open/close spikes; VWAP and session high/low matter intraday.

**Links:** [01 Market Basics](../stock-market-analysis/technical-analysis/handbook/01-market-basics/README.md)

---

## 2. Price Action

- **Support/Resistance:** Levels where price tends to hold or reverse. Multiple touches strengthen level; break + retest = role reversal (resistance becomes support).
- **Trendlines:** Uptrend line along higher lows; downtrend line along lower highs. Channels = parallel boundaries. Break of trendline can signal weakening trend.
- **Structure:** Uptrend = HH + HL; downtrend = LH + LL. **Break of structure (BOS)** = break of prior HH or LL (continuation or new trend). **Market structure shift (MSS)** = e.g. first LL in uptrend = bearish shift.
- **Liquidity:** Stops cluster above highs / below lows. **Liquidity grab** = sweep of those levels then reversal; use as setup or avoid placing stops exactly there.
- **Range vs trend:** Range = horizontal S/R; trade fades or wait for breakout. Trend = trade in direction with structure (pullbacks, BOS).

**Links:** [02 Price Action](../stock-market-analysis/technical-analysis/handbook/02-price-action/README.md)

---

## 3. Candlestick Analysis

- **Anatomy:** Body (open–close); wicks (rejection at high/low). Context (trend, level) matters more than pattern alone.
- **Single:** Doji (indecision); Hammer (bullish at support); Hanging Man / Shooting Star (bearish at top); Inverted Hammer (bullish at support); Marubozu (strong body).
- **Two:** Bullish/Bearish Engulfing; Piercing Line; Dark Cloud Cover; Tweezer Top/Bottom. Confirm with next candle.
- **Three:** Morning Star (bullish); Evening Star (bearish); Three White Soldiers / Three Black Crows; Inside Bar (breakout); Outside Bar (expansion). Entry on confirmation; stop beyond pattern.

**Links:** [03 Candlestick Analysis](../stock-market-analysis/technical-analysis/handbook/03-candlestick-analysis/README.md)

---

## 4. Chart Patterns

- **Reversal:** Head & Shoulders (break below neckline); Inverse H&S (break above); Double/Triple Top/Bottom; Rounded Top/Bottom. Measured move = height projected from break. Volume confirms break.
- **Continuation:** Bull/Bear Flag (break in trend direction; target = flagpole length); Pennant; Ascending/Descending/Symmetrical Triangle; Rectangle; Cup and Handle. Stop opposite side of pattern.
- **Breakouts:** Require **close** beyond level and preferably **volume**. False breakouts common—retest or buffer stop. Invalidate if price closes back inside.

**Links:** [04 Chart Patterns](../stock-market-analysis/technical-analysis/handbook/04-chart-patterns/README.md)

---

## 5. Technical Indicators

- **Trend:** MA, EMA (9,20,50,200); VWAP (intraday); Ichimoku (cloud, Tenkan, Kijun); Parabolic SAR (trailing stop). Best in trending markets.
- **Momentum:** RSI (0–100; >70 overbought, <30 oversold; divergence); MACD (crossover, zero line, divergence); Stochastic; CCI. Use in range for mean reversion; in trend for divergence.
- **Volatility:** Bollinger Bands (squeeze, band touches); ATR (stops, targets); Keltner. No direction—only size of move.
- **Volume:** Volume profile (POC, value area); OBV; A/D; VWAP Anchored. Confirm breakouts and trend.

**Links:** [05 Technical Indicators](../stock-market-analysis/technical-analysis/handbook/05-technical-indicators/README.md)

---

## 6. Advanced Concepts

- **Order blocks:** Last opposing candle before strong move; zone for retest (support/resistance). Trade with structure.
- **Liquidity zones:** Above highs / below lows; sweeps = liquidity grab. Don’t place stops exactly there.
- **Fair Value Gap (FVG):** Three-candle imbalance; often filled. Entry on fill in trend direction.
- **Wyckoff:** Accumulation (spring = false breakdown) → markup; Distribution (upthrust = false breakout) → markdown. Volume confirms.

**Links:** [06 Advanced Concepts](../stock-market-analysis/technical-analysis/handbook/06-advanced-concepts/README.md)

---

## 7. Trading Strategies

- **Trend following:** Pullbacks to structure (HL, EMA); BOS confirmation. Stop below HL (long). R:R 1:2 or 1:3.
- **Breakout:** Close beyond range/pattern; volume; stop opposite side; target = measured move.
- **Mean reversion:** Fade at support/resistance (and RSI/Stochastic). Best in range. Tight stop; 1:1 or 1:1.5 R:R.
- **Scalp:** Short hold; small target; tight stop; liquid names; factor in costs.
- **Swing:** Multi-day; 4H/daily structure; stop below swing low; target next structure or 1:2 R:R.
- **Position:** Weekly/daily; wide stop; small size; trail structure.

**Links:** [07 Trading Strategies](../stock-market-analysis/technical-analysis/handbook/07-trading-strategies/README.md)

---

## 8. Risk Management & Psychology

- **Position size:** Dollar risk = Account × Risk% (e.g. 1%). Size = Dollar risk / |Entry − Stop|. Stop defined **before** entry.
- **R:R:** Aim ≥ 1:1.5 or 1:2. Expectancy = (Win% × Avg win) − (Loss% × Avg loss) > 0.
- **Drawdown:** Plan for 10–20%. Reduce size or pause after limit. No doubling up to recover.
- **Psychology:** Discipline (follow plan); avoid revenge trading and overtrading; journal every trade; written trading plan; awareness of biases (confirmation, recency, FOMO).

**Links:** [08 Risk Management](../stock-market-analysis/technical-analysis/handbook/08-risk-management/README.md) | [09 Trading Psychology](../stock-market-analysis/technical-analysis/handbook/09-trading-psychology/README.md)

---

## 9. Backtesting & Algo

- **Backtest:** Rules on historical data; include costs; avoid look-ahead and overfitting. Metrics: win rate, expectancy, max drawdown, profit factor.
- **Walk-forward:** Optimize in-sample; test out-of-sample; roll forward. Forward test (paper/small live) before full size.
- **Algo:** Code rules → backtest → paper → live. APIs for data and execution; Python (pandas, backtrader/vectorbt).

**Links:** [10 Backtesting](../stock-market-analysis/technical-analysis/handbook/10-backtesting/README.md) | [11 Algorithmic Trading](../stock-market-analysis/technical-analysis/handbook/11-algorithmic-trading/README.md)

---

## 10. Common Mistakes

- No plan, no stop, oversized position, chasing, too many symbols/timeframes, no journal.
- Indicator overload → use few; filter by context. Ignoring context → don’t trade same signal in all conditions.
- Overleveraging → cap leverage; size by risk%. Chasing → wait for setup; “no trade” is OK.

**Links:** [12 Common Mistakes](../stock-market-analysis/technical-analysis/handbook/12-common-mistakes/README.md) | [Revision](../Revision/Complete_Trading_Revision.md)
