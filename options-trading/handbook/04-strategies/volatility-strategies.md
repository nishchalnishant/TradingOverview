# Volatility Strategies

Volatility strategies are not primarily directional — they profit from the magnitude of price moves (long vol) or from the absence of large moves (short vol). The key variable is whether implied volatility is cheap or expensive relative to expected realized volatility.

---

## Long Straddle

### Setup

Buy an ATM call and an ATM put at the same strike and expiration.

```
P&L at expiration:
      /\
     /  \  break-even above and below
    /    \
───/──────\───────────────────── stock price
  /        \
(cost)     (cost)
```

| Parameter | Detail |
|-----------|--------|
| Bias | No directional bias; want large move either way |
| Cost | Call premium + put premium (net debit) |
| Max risk | Total debit paid |
| Max reward | Unlimited to upside; strike − debit to downside |
| Upper breakeven | Strike + total debit |
| Lower breakeven | Strike − total debit |
| Best environment | Low IV before an expected large move (pre-event) |
| Greeks | Long delta (zero initially), long gamma, negative theta, long vega |

### Payoff Example

Stock at $100. Buy 100 Call at $3.50 and 100 Put at $3.00 (30 DTE).
- Total debit: $6.50
- Upper breakeven: $106.50
- Lower breakeven: $93.50
- Profit at $115: (115 − 100) − 6.50 = $8.50 per share ($850)
- Profit at $85: (100 − 85) − 6.50 = $8.50 per share ($850)
- Loss if stock stays at $100: −$6.50

### When to Use

- Before a known event (earnings, FDA, macro event) when you believe the move will exceed the options market's priced-in expected move
- When IV is low and you expect a spike
- Compute the market's expected move: ≈ ATM call + ATM put. If you think the actual move will be larger, the straddle has positive expected value.

### Key Risk

Theta decay. A straddle pays maximum theta — you are long both calls and puts, both decaying. In a straddle bought 30 DTE, roughly 50% of the value decays in the first 15 days and 50% in the final 15 days. Don't hold a long straddle for weeks without a catalyst.

---

## Long Strangle

### Setup

Buy an OTM call and an OTM put at different strikes, same expiration.

| Feature vs Straddle | Strangle |
|--------------------|----------|
| Cost | Lower (OTM options cheaper) |
| Required move to profit | Larger (strikes are further from stock price) |
| Max risk | Total debit (same concept) |
| Breakeven range | Wider gap between upper and lower breakevens |
| Theta sensitivity | Lower absolute theta (cheaper position) |

### Payoff Example

Stock at $100. Buy 105 Call at $2.00, Buy 95 Put at $1.80 (30 DTE).
- Total debit: $3.80
- Upper breakeven: $108.80
- Lower breakeven: $91.20
- Profit if stock moves to $115: (115 − 105) − 3.80 = $6.20 ($620)

### Strangle vs Straddle: Which to Choose

| Scenario | Better choice |
|----------|--------------|
| Strong expectation of a very large move | Straddle (maximize gamma for the same dollar move) |
| Moderate expectation of a sizeable move | Strangle (lower cost reduces break-even hurdle) |
| Very low IV environment | Either; straddle captures more gamma at current price |
| Post-event expected continuation | Usually straddle to capture continuation in either direction |

---

## Short Straddle

### Setup

Sell an ATM call and an ATM put at the same strike and expiration.

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral; want stock to pin at the strike |
| Credit received | Call premium + put premium |
| Max reward | Total credit received |
| Max risk | Unlimited to upside; Strike − credit to downside (stock to zero) |
| Profit range | Within breakevens: strike ± credit |
| Best environment | High IV; expect IV to fall and stock to stay near strike |
| Risk | NAKED — requires margin; large moves cause large losses |

### Short Straddle Risk

The short straddle is one of the most margin-intensive and risky structures. It is only appropriate for experienced traders with strict risk management:

- A 2σ move against you can cause a loss 3–5× the premium collected
- Gamma spikes near expiration — even a small move in the last week can cause large delta changes
- Consider using iron condors or iron butterflies instead, which are defined-risk equivalents

---

## Short Strangle

### Setup

Sell an OTM call and an OTM put at different strikes, same expiration.

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral; want stock to stay between the short strikes |
| Credit | OTM call premium + OTM put premium |
| Max reward | Total credit received |
| Max risk | Unlimited (put side: stock to zero; call side: unlimited) |
| Profit range | Between put strike and call strike |
| Best environment | High IV, low gamma environment |

### Short Strangle vs Iron Condor

| Feature | Short Strangle | Iron Condor |
|---------|---------------|------------|
| Max loss | Undefined/large | Capped (spread width − credit) |
| Premium collected | Higher | Lower (long wings cost money) |
| Margin required | High (naked) | Defined by spread width |
| Risk management | Difficult | Straightforward |
| Recommended for | Experienced traders, smaller positions | All experience levels |

**Practical guidance:** Most retail traders should use iron condors rather than naked short strangles. The extra premium from going naked is rarely worth the undefined risk and margin complexity.

---

## Long Vol vs Short Vol: When to Use Each

| Environment | Long Vol (Buy) | Short Vol (Sell) |
|-------------|----------------|-----------------|
| **IV rank** | < 30% | > 50% |
| **Pre-event** | Yes (straddle/strangle before catalyst) | No — event risk too high |
| **Post-event (IV crush)** | No | Yes — IV has reset, sell new premium |
| **VIX below 15** | Yes — cheap historical hedge | No — selling at low premium |
| **VIX above 30** | No — IV is expensive | Yes — but use defined risk |
| **Quiet trending market** | No | Yes — low realized vol |
| **Volatile, choppy market** | Yes | Avoid short naked structures |

---

## Calendar Spread

### Setup

Sell a near-term option, buy a longer-term option at the same strike.

```
Today:
  Sell: 45-DTE ATM call at $3.50
  Buy:  90-DTE ATM call at $5.50
  Net debit: $2.00
```

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral; want stock near the strike on near-term expiry |
| Cost | Net debit (back-month more expensive than front-month) |
| Max reward | When short option expires worthless and back-month retains value |
| Max risk | Debit paid (both options move against you) |
| Vega | Net long vega (back-month has more vega than front-month) |
| Theta | Net positive theta (front-month decays faster than back-month) |

### How Calendar Spreads Profit

1. **Time decay differential:** Front-month option decays faster (higher theta) than the back-month. If stock pins near the strike, the front-month expires worthless and you own the back-month for $2.00 (paid $5.50 for a $3.50 option effectively).

2. **IV expansion:** If IV rises (long vega position), the back-month option gains more value than the front-month loses. Calendar spreads benefit from IV spikes if the stock doesn't move too far.

### Calendar Spread Ideal Setup

- **Stock pins near the strike** at front-month expiration → short option expires worthless
- **IV is flat or in contango** (normal term structure) → back-month has reasonable premium
- **Do not use in backwardation** — near-term IV is artificially high; you are selling the expensive vol and buying the cheaper vol, the opposite of the calendar's edge

### Double Calendar and Diagonal

- **Double calendar:** Two calendar spreads at different strikes (one above, one below current price) — similar to iron condor but with time as the axis
- **Diagonal spread:** Buy back-month at one strike, sell front-month at a different strike — combines calendar's time dimension with vertical spread's directional bias; common in LEAPS + short-term call (poor man's covered call)

---

## Summary: Volatility Strategy Selection

| Strategy | Debit/Credit | Long/Short Vol | Best IVR | Max Risk |
|----------|-------------|---------------|---------|---------|
| Long straddle | Debit | Long | < 30% | Debit paid |
| Long strangle | Debit | Long | < 30% | Debit paid |
| Short straddle | Credit | Short | > 50% | Unlimited |
| Short strangle | Credit | Short | > 50% | Unlimited |
| Iron condor | Credit | Neutral | > 50% | Spread width − credit |
| Calendar spread | Debit | Long vega | Low/contango | Debit paid |
