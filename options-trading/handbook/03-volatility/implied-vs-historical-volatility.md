# Implied vs Historical Volatility

## Historical Volatility (HV)

Historical volatility (also called realized volatility or statistical volatility) measures how much the stock actually moved over a past period. It is computed from the stock's daily log returns.

### Calculation

1. Compute daily log returns: r_t = ln(P_t / P_{t-1})
2. Calculate the standard deviation of those returns over the lookback period (e.g., 20 or 30 trading days)
3. Annualize: HV = σ_daily × √252

```
Example:
  30-day average daily log return std dev = 1.2%
  Annualized HV = 1.2% × √252 ≈ 19%
```

### Common Lookback Periods

| Period | Sensitivity | Use case |
|--------|------------|---------|
| 10-day HV | Very sensitive to recent moves | Short-term realized vol comparison |
| 20-day HV | Moderate | Compare to 30-DTE IV |
| 30-day HV | Standard | Compare to VIX (30-day measure) |
| 60-day HV | Slower | Longer-term context |

Always match the HV lookback to the option's time to expiration for a meaningful comparison.

---

## Implied Volatility (IV)

Implied volatility is the volatility parameter that, when plugged into Black-Scholes, produces the market's observed option price. It is **extracted (implied) from the market price**, not calculated from historical data.

IV is forward-looking — it reflects market consensus on how much the stock is expected to move over the option's life.

### How IV Is Quoted

- Expressed as an annualized percentage (e.g., IV = 35% means the market implies a ~35% one-standard-deviation annual move)
- Varies by strike and expiration (this variation is the volatility skew/surface — see next file)
- The most common reference is the **ATM implied volatility** for a given expiration

### Computing Expected Moves from IV

| Timeframe | Formula | Example (IV=40%, S=$100) |
|-----------|---------|--------------------------|
| Annual (1 SD) | S × IV | $40 |
| Monthly | S × IV / √12 | $11.55 |
| Weekly | S × IV / √52 | $5.55 |
| Daily | S × IV / √252 | $2.52 |

The "1 SD expected move" means the stock is expected to stay within that range approximately 68% of the time over that period.

---

## IV vs HV: The Key Comparison

The relationship between IV and HV is the foundation of volatility trading edge.

| Condition | Meaning | Who benefits |
|-----------|---------|-------------|
| **IV > HV** (vol premium) | Options priced above realized vol; market overestimates future moves | Sellers — collect inflated premium |
| **IV ≈ HV** | Fair pricing; no structural edge | Neutral |
| **IV < HV** | Options cheap; market underestimates future moves | Buyers — cheap options relative to realized vol |

**On average, IV > HV.** The difference (IV − HV) is the "volatility risk premium" — the compensation sellers earn for providing liquidity and bearing tail risk. Studies on equity indices show this premium has historically been 2–5 vol points on average.

### Practical Interpretation

- AAPL IV = 28%, 30-day HV = 18% → options are expensive → lean toward selling premium
- TSLA IV = 55%, 30-day HV = 70% → stock is actually moving more than IV predicts → options are cheap → lean toward buying premium

However: HV is backward-looking. Events (earnings, product launches) can cause future realized vol to spike above recent HV. This is why simply selling options before volatile events based on IV > HV can be dangerous.

---

## VIX: The Market Fear Gauge

The VIX (CBOE Volatility Index) measures the 30-day implied volatility of S&P 500 options. It is the most widely watched volatility gauge.

### VIX Levels and Context

| VIX Level | Market Regime | Options Strategy Implication |
|-----------|--------------|------------------------------|
| < 12 | Extreme complacency | Very cheap options; consider long vol |
| 12–16 | Low vol | Options cheap; slightly favor buyers |
| 16–20 | Normal | Balanced; both strategies viable |
| 20–25 | Elevated | Above-average IV; favor sellers |
| 25–35 | High vol | Elevated premium; strong seller's edge but gamma risk is high |
| > 35 | Crisis/spike | Extremely elevated; selling is tempting but dangerous; wait for stabilization |

### VIX Term Structure

The VIX futures term structure shows how the market prices volatility at different time horizons.

- **Contango (normal):** Near-term VIX < longer-dated VIX futures. Market is calm now but expects uncertainty to persist. This is the usual state.
- **Backwardation (stress):** Near-term VIX > longer-dated VIX futures. Current crisis is expected to be temporary.

Term structure backwardation is a signal of **acute market stress** and often coincides with the best opportunity to sell short-dated elevated IV.

---

## Volatility Mean Reversion

Volatility is one of the most reliably mean-reverting variables in financial markets. High vol periods are followed by lower vol; low vol periods are followed by higher vol.

Mechanism:
- High IV attracts premium sellers who increase supply of options, pushing IV down
- Low IV deters sellers; demand for options (hedging, speculation) accumulates; a catalyst causes a vol spike
- After a spike, realized vol eventually slows; IV collapses back toward historical norms

### Practical Implications

- Don't sell vol into a spike at the first sign of elevated IV — wait for the spike to peak and show signs of reversal
- Don't buy vol during extended low-IV regimes — cheap options can stay cheap for months
- Use **IVR > 50%** as a trigger for selling strategies, not the absolute IV level

---

## IV Rank (IVR) and IV Percentile: Comparing IV to History

Raw IV is not enough context. Always compare current IV to its history.

### IV Rank (IVR)

```
IVR = (Current IV − 52-week Low IV) / (52-week High IV − 52-week Low IV) × 100
```

Example: Stock with 52-week IV range of 20%–60%, current IV = 45%:
- IVR = (45 − 20) / (60 − 20) × 100 = **62.5%** → elevated → lean toward selling

**Limitation:** One large spike (e.g., from a gap-down) can set a high "52-week high" that makes all subsequent IV look low by comparison for months.

### IV Percentile

What percentage of days in the past year had IV lower than today's level.

- More robust than IVR because it reflects the full distribution, not just the min/max
- IV Percentile of 80% means IV was lower than today 80% of the year → elevated

### Trading Rules Based on IV Rank

| IVR | Strategy |
|-----|---------|
| > 50% | Sell premium: credit spreads, iron condors, short strangles, covered calls |
| 30–50% | Neutral: debit spreads acceptable; avoid naked long or short vol |
| < 30% | Buy premium: debit spreads, long straddles/strangles when a catalyst is expected |

These thresholds are guidelines, not rigid rules. Always combine IVR with:
- Upcoming catalyst calendar (earnings, FDA, FOMC)
- Term structure shape (is the near-term IV elevated relative to the back months?)
- Stock-specific context

---

## Connecting IV and HV to Position Management

| Situation | Action |
|-----------|--------|
| IV spikes 30%+ above recent HV, no event pending | Sell short-term options to capture mean reversion |
| IV below 30-day HV, event approaching | Avoid selling options; the realized move may exceed IV |
| IV crush just occurred (post-earnings) | Consider selling new premium as IV has reset lower |
| Extended low-vol regime | Hedge with cheap puts; avoid selling premium at historically low prices |
