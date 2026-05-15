# Options with Technical Analysis

Technical analysis informs options trading in four key ways: timing entries and exits, selecting the right expiration for a given time horizon, using price volatility metrics (ATR) to select strikes, and treating support/resistance levels as structural boundaries for option positions.

---

## Using TA for Entry and Exit Timing

Technical analysis provides entry and exit signals that are just as applicable to options positions as to stock trades — but the timing implications are more critical because options have expiration dates and time decay.

### Entry Timing

| TA Signal | Options application |
|-----------|-------------------|
| Breakout above resistance with volume | Enter long call or bull call spread; buy into the breakout or on the first pullback to the level |
| Bullish reversal at support (hammer, engulfing) | Enter long call or sell put spread below support |
| Moving average crossover (bullish) | Enter long call or reduce hedge (close puts) |
| Oversold RSI at support | Enter long call with catalyst; or sell a put spread below support |
| Bearish breakdown below support | Enter long put or bear put spread; confirms trend has shifted |

### Why Timing Matters More in Options

A stock trade entered one week early loses opportunity cost. An options trade entered one week early loses both opportunity cost and theta decay. On a 30-day option, one wasted week costs approximately 30% of the option's time value.

**Rule:** For short-dated (30–60 DTE) directional options, only enter at a clear technical trigger. Do not "pre-position" waiting for a move that might take weeks.

### Exit Timing via TA

Technical signals can also improve exits:
- **Approaching resistance:** If long a call and stock approaches a major resistance level, consider taking partial profit even if options target hasn't been reached. Resistance may stall the move.
- **Breakdown below entry support:** If the technical support that justified a long call position breaks, consider exiting even with time remaining. The original thesis is invalidated.
- **Overbought reading at resistance:** For a covered call position, if the underlying shows RSI divergence at your call strike, the call is unlikely to be breached — hold through expiry confidently.

---

## Aligning Option Expiration with TA Time Horizon

One of the most common mistakes: buying a 30-day option for a 6-week thesis. Matching DTE to the expected timeframe of the technical move is essential.

### Expiration Selection Framework

| Technical pattern / catalyst | Expected timeframe | Minimum DTE to use |
|-----------------------------|-------------------|--------------------|
| Earnings play (directional) | 1–2 days | 7–14 DTE (day of earnings, close before) |
| Bull flag breakout | 1–3 weeks | 30–45 DTE |
| Resistance break on weekly chart | 4–8 weeks | 60–90 DTE |
| Head-and-shoulders top | 6–12 weeks | 90–120 DTE |
| Long-term base breakout / cup-and-handle | 3–6 months | 120–180 DTE or LEAPS |
| Sector rotation thesis | 3–6 months | 90–180 DTE |

**Add a buffer:** If your TA says the move should happen in 3 weeks, buy a 6-week option. You pay slightly more, but avoid the situation where the move is slightly delayed and theta destroys the trade before it plays out.

**DTE and delta relationship:** For longer time horizons, you can afford more OTM strikes (lower delta) because there is more time for the move. For very short-dated trades, stick to ATM or slight OTM to maximize probability.

---

## Using ATR to Size Expected Moves and Select Strikes

**Average True Range (ATR)** measures the typical daily price range of a stock. It is one of the most useful tools for calibrating options strike selection and determining whether a position is reasonable.

### Computing Expected Move with ATR

```
Daily ATR (14-period) = average of daily high − low (or close-to-close range) over 14 days

Expected move in N days (rough) = ATR × √N

Example:
  AAPL daily ATR = $3.00 (stock at $170)
  Expected 30-day move ≈ $3.00 × √30 ≈ $3.00 × 5.48 ≈ $16.40

  This implies:
  - Upside breakeven: $186.40
  - Downside breakeven: $153.60
```

### ATR for Strike Selection

Use ATR-based expected moves to choose strikes that are:
- **For long directional options:** Strikes within 1–1.5 ATR-move of current price for a given DTE (giving realistic chance of being ITM at expiry)
- **For short premium (income):** Short strikes beyond 2× ATR move for the DTE → low probability of being breached

| Purpose | Strike distance | Example (ATR=$3, 30DTE expected $16.40 move) |
|---------|----------------|----------------------------------------------|
| Aggressive long call | ATM or slight OTM | 170 call (ATM) or 175 call |
| Moderate long call | 0.5–1 ATR above | 173 call |
| Conservative call (low delta) | 1.5–2 ATR above | 178–185 call |
| Short put for income | 1.5–2 ATR below | Short put at 153–160 |
| Very conservative short put | 2–3 ATR below | Short put at 146–150 |

### ATR vs Implied Move

Compare the ATR-based expected move to the options market's implied move (ATM call + ATM put premium):

- If **ATR expected move > options implied move**: the stock moves more than options price in → options may be cheap → lean toward buying
- If **ATR expected move < options implied move**: stock moves less than options pricing → options may be overpriced → lean toward selling

---

## Support and Resistance as Stop Equivalents for Option Trades

Stock traders use stop-loss orders at support/resistance levels. Options traders don't usually set stop orders on the option itself (bid-ask spread can trigger poor fills). Instead, use the underlying's technical levels as the trigger to close the options position.

### Structural Stops via TA

| Position | Technical stop signal | Action |
|----------|----------------------|--------|
| Long call (bullish) | Underlying closes below major support | Close the call; thesis invalidated |
| Long put (bearish) | Underlying closes above major resistance | Close the put; thesis invalidated |
| Bull put spread | Underlying breaks below short put strike on a closing basis | Close or roll the spread |
| Iron condor | Underlying breaks beyond one of the short strikes | Close threatened side; evaluate full position |

**Key distinction:** A temporary intraday pierce of a level is not the same as a close below it. Wait for a daily close beyond the level before treating it as a stop trigger — options have wide intraday bid-ask and reacting to intraday noise is costly.

### Calculating Option Exit Price from Underlying Level

Before entry, compute what the option price will approximately be if the technical stop level is hit:

```
Current stock: $100, call strike $102, call price $2.50 (delta=0.45)
Technical stop: $97 (support level)

If stock reaches $97:
  Approximate call price = $2.50 − (3.00 × 0.45) ≈ $2.50 − $1.35 ≈ $1.15

  You would close the call at ~$1.15, a loss of $1.35 per share ($135/contract)
```

This calculation allows you to properly size the position before entry using the underlying's technical stop rather than an arbitrary option price stop.

---

## Multi-Timeframe Analysis for Options Timing

Apply multi-timeframe analysis (MTFA) to confirm that option trades have alignment across time horizons.

### Three-Timeframe Framework for Options

| Timeframe | Purpose | Example for 30-DTE option |
|-----------|---------|--------------------------|
| **Weekly chart** | Define the primary trend and major S/R | Is the stock in an uptrend? Is a major level nearby? |
| **Daily chart** | Confirm the tactical setup | Is there a bullish reversal pattern? Is momentum turning? |
| **4-hour/hourly chart** | Precise entry timing | Where exactly is the entry trigger? |

**Alignment rule:** Only enter a directional options trade when at least 2 of 3 timeframes are aligned. Avoid trading against the weekly trend with a short-dated option — you are fighting time decay AND trend simultaneously.

### Example: MTFA for a Bullish Call

- **Weekly:** Stock in a multi-month uptrend; pulled back to the rising 20-week MA. Trend is up.
- **Daily:** Bullish engulfing candle at the pullback level. RSI divergence at 45. Support confirmed.
- **Hourly:** Morning gap fill; strong bounce from the level with above-average volume.

All three timeframes align bullishly. Buy a 45-DTE call at the daily support level, strike one tick above the weekly MA level. Stop: daily close below the weekly MA.

---

## Summary: TA-Options Integration Rules

| Rule | Detail |
|------|--------|
| Enter at technical triggers only | Don't buy time-sensitive options waiting for a move; wait for confirmation |
| Match DTE to TA time horizon | Breakout → 30–60 DTE; base breakout → 90–180 DTE; always add buffer |
| Use ATR for strike selection | Place short strikes beyond 2× ATR-move; long strikes within 1× ATR-move |
| Use underlying S/R as options stop | Close option when underlying closes beyond the invalidating technical level |
| Multi-timeframe alignment | Require 2 of 3 timeframes to agree before entering directional options |
| Manage at resistance/support levels | Don't hold into a level; take partial profits or tighten stops at major S/R |
