# Complete Trading Revision — Summary of the Handbook

Quick recall of key concepts from the Technical Analysis & Trading Handbook. Use for exam-style revision and fast lookup.

---

## 1. Market Basics

| Concept | Definition |
|--------|------------|
| **Bid** | Highest price buyers are willing to pay |
| **Ask** | Lowest price sellers will accept |
| **Spread** | Ask − Bid; cost of round-trip |
| **Market order** | Execute immediately at best available price |
| **Limit order** | Execute only at your price or better |
| **Stop order** | Becomes market order when price hits level |
| **Liquidity** | Ability to trade without moving price much |
| **Order flow** | Stream of buy/sell orders; imbalance moves price |
| **Sessions** | Asian, London, NY; London+NY overlap = highest FX volatility |

---

## 2. Price Action

| Concept | Definition |
|--------|------------|
| **Support** | Level where buying tends to appear; price holds/bounces |
| **Resistance** | Level where selling tends to appear; price rejects |
| **HH/HL** | Higher High, Higher Low = uptrend structure |
| **LH/LL** | Lower High, Lower Low = downtrend structure |
| **BOS** | Break of structure (break of prior HH or LL) |
| **MSS / CHoCH** | Market structure shift; e.g. first LL in uptrend = bearish shift |
| **Liquidity grab** | Price sweeps stops (e.g. below low) then reverses |
| **Range** | Price between horizontal S/R; no clear trend |
| **Trend** | Clear HH/HL or LH/LL; trade in direction |

---

## 3. Candlestick Patterns (Quick)

- **Single:** Doji (indecision), Hammer (bullish at support), Hanging Man (bearish at top), Shooting Star (bearish at top), Inverted Hammer (bullish at support), Marubozu (strong body, no wicks).
- **Two:** Bullish/Bearish Engulfing, Piercing Line (bullish), Dark Cloud Cover (bearish), Tweezer Top/Bottom.
- **Three:** Morning Star (bullish), Evening Star (bearish), Three White Soldiers (bullish), Three Black Crows (bearish), Inside Bar (consolidation), Outside Bar (expansion).
- **Context:** Always consider trend and level; confirmation (next candle) before entry.

---

## 4. Chart Patterns (Quick)

- **Reversal:** Head & Shoulders (bearish), Inverse H&S (bullish), Double Top/Bottom, Triple Top/Bottom, Rounded Top/Bottom. Trade **break** of neckline with confirmation.
- **Continuation:** Bull/Bear Flag, Pennant, Ascending/Descending/Symmetrical Triangle, Rectangle, Cup and Handle. Trade **breakout** in trend direction.
- **Breakout:** Prefer **close** beyond level + **volume**; beware false breakouts (retest or buffer stop).

---

## 5. Technical Indicators (Quick)

- **Trend:** MA, EMA, VWAP, Ichimoku, Parabolic SAR. Best in **trending** markets.
- **Momentum:** RSI (0–100; >70 overbought, <30 oversold), MACD (crossover, zero line, divergence), Stochastic, CCI. Use in **range** for overbought/oversold; in **trend** for divergence or pullback.
- **Volatility:** Bollinger Bands (squeeze, mean reversion), ATR (stops, targets), Keltner. **No direction**—only size of move.
- **Volume:** Volume profile (POC, value area), OBV, A/D, VWAP Anchored. **Confirm** breakouts and trend.

---

## 6. Advanced Concepts

- **Order block:** Last opposing candle before strong move; zone for retest (support/resistance).
- **Liquidity zones:** Above highs / below lows (stops); sweeps then reversal = liquidity grab.
- **FVG (Fair Value Gap):** Three candles, middle doesn’t overlap first; often “filled” later. Entry on fill in trend direction.
- **Wyckoff:** Accumulation (spring = false breakdown) → markup; Distribution (upthrust = false breakout) → markdown. Volume confirms.

---

## 7. Trading Strategies (Quick)

- **Trend following:** Enter pullbacks to structure (HL, EMA) or BOS in trend direction. Stop below HL (long).
- **Breakout:** Enter on close beyond range/pattern; stop opposite side; target = measured move.
- **Mean reversion:** Fade extremes at support/resistance (and/or RSI overbought/oversold). Best in **range**.
- **Scalp:** Short hold; small target; tight stop; liquid instruments; low cost.
- **Swing:** Multi-day; structure and levels; 1:2 or 1:3 R:R.
- **Position:** Long-term; weekly/daily structure; wide stop; small size.

---

## 8. Risk Management

- **Risk per trade:** 0.5–2% (e.g. 1%). Dollar risk = Account × Risk%.
- **Position size:** Size = Dollar risk / |Entry − Stop|.
- **R:R:** Aim ≥ 1:1.5 or 1:2. Expectancy = (Win% × Avg win) − (Loss% × Avg loss) > 0.
- **Drawdown:** Plan for 10–20%; reduce size or pause after hitting limit. No doubling up to recover.
- **Correlation:** Diversify; avoid too many correlated positions.

---

## 9. Trading Psychology

- **Discipline:** Follow plan and rules; don’t close early or skip stop.
- **Fear/greed:** Fear → early exit, avoid setups. Greed → overtrading, overleveraging, hold losers.
- **Revenge trading:** No trade to “get back” a loss; pause after loss.
- **Overtrading:** Only trade valid setups; cap trades per day.
- **Journal:** Log setup, entry, exit, P&L, emotion; review weekly.
- **Plan:** Written rules (entry, exit, stop, size, when not to trade).
- **Biases:** Confirmation, recency, anchoring, loss aversion, overconfidence, FOMO—awareness and rules reduce them.

---

## 10. Backtesting & Algo

- **Backtest:** Run strategy on history; include costs; avoid look-ahead and overfitting.
- **Walk-forward:** Optimize in-sample; test out-of-sample; roll forward.
- **Forward test:** Paper or small live after backtest; final validation.
- **Overfitting:** Too many parameters; strategy fails on new data. Keep simple; test multiple instruments and periods.
- **Algo:** Code rules → backtest → paper → live. APIs for data and execution; Python stack (pandas, backtrader/vectorbt).

---

## 11. Common Mistakes

- No plan, no stop, size too big, chasing, too many symbols/timeframes, no journal.
- **Indicator overload:** Use few indicators; filter by context (trend, level).
- **Context:** Don’t trade same signal in all conditions (e.g. RSI oversold in strong downtrend).
- **Overleveraging:** Cap leverage; size so one trade doesn’t blow account.
- **Risk:** Fixed risk%, max daily loss, no moving stop against you, no adding to losers.
- **Chasing:** Wait for setup; “no trade” is OK.

---

## Key Charts (ASCII)

**Uptrend (HH/HL):**
```
      ●  HH
     / \
    ●   ●  HL
```

**Head and Shoulders:**
```
    ●   RS
   / \   ●  Head
  ●   \ / \
 LS    \___
         Neckline
```

**Bull Flag:**
```
  ═══●  Break
  │ ╱╲
  │╱  ╲ Flag
  ●════  Pole
```

---

*For full detail, see the [Handbook](stock-market-analysis/technical-analysis/handbook/README.md).*
