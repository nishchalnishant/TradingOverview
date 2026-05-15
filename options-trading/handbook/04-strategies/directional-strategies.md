# Directional Strategies

Directional options strategies profit from a move in the underlying asset. They differ from simply buying stock by offering leverage, defined risk, and the ability to profit on either side without margin requirements (for long options).

---

## Long Call

### Setup

Buy a call option on a bullish underlying.

| Parameter | Detail |
|-----------|--------|
| Bias | Bullish |
| Cost | Debit (premium paid) |
| Max risk | Premium paid |
| Max reward | Unlimited (stock can rise indefinitely) |
| Breakeven at expiry | Strike + premium paid |
| Delta | Positive (0.15–0.80 depending on strike) |
| Theta | Negative (time enemy) |
| Best IV environment | Low IV (cheap options) |

### Payoff Example

Stock at $100. Buy 105 Call for $2.00 (30 DTE):
- Breakeven: $107.00
- At $110: profit = (110 − 105) − 2.00 = $3.00 ($300 per contract)
- At $104: expires worthless, loss = −$2.00 ($200)

### When to Use

- Strong bullish conviction with a specific catalyst (earnings surprise, product launch, sector rotation)
- When you want leveraged upside with strictly capped downside
- When IV is low (IVR < 30%): the option is cheap relative to history
- Time horizon matches DTE: don't buy a 30-day call for a 6-week thesis

---

## Long Put

### Setup

Buy a put option on a bearish underlying.

| Parameter | Detail |
|-----------|--------|
| Bias | Bearish |
| Cost | Debit (premium paid) |
| Max risk | Premium paid |
| Max reward | Strike − premium (stock goes to zero) |
| Breakeven at expiry | Strike − premium paid |
| Delta | Negative (−0.15 to −0.80) |
| Theta | Negative |
| Best IV environment | Low IV |

### Payoff Example

Stock at $100. Buy 95 Put for $2.00 (30 DTE):
- Breakeven: $93.00
- At $88: profit = (95 − 88) − 2.00 = $5.00 ($500 per contract)
- At $97: expires worthless, loss = −$2.00

### When to Use

- Bearish thesis with identified catalyst (deteriorating fundamentals, technical breakdown, macro headwind)
- Hedging against a long stock position (see Section 5 — Hedging Strategies)
- Short-selling substitute: defined max loss, no borrow cost, no margin call

---

## Comparing Long Options vs Spreads

| Feature | Long Option | Vertical Spread |
|---------|-------------|----------------|
| Cost | Higher debit | Lower debit (offset by selling strike) |
| Max profit | Unlimited (call) or large (put) | Capped (spread width − debit) |
| Max loss | Premium paid | Debit paid |
| Breakeven | Strike + premium | Strike of bought option + debit |
| IV sensitivity | High positive vega | Reduced vega (two legs partially offset) |
| IV environment | Best in low IV | Works in more IV environments |

**Key trade-off:** Vertical spreads cost less and reduce IV risk, but they cap the maximum profit. Use long options when you expect a large move; use spreads when you expect a moderate move and want to reduce cost.

---

## Bull Call Spread

### Setup

Buy a lower-strike call, sell a higher-strike call at the same expiration.

| Parameter | Detail |
|-----------|--------|
| Bias | Bullish (moderate move) |
| Cost | Net debit = price of long call − price of short call |
| Max risk | Net debit paid |
| Max reward | Spread width − net debit |
| Breakeven at expiry | Lower strike + net debit |
| Best IV environment | Low-to-moderate IV |

### Payoff Example

Stock at $100. Buy 100 Call at $4.00, Sell 110 Call at $1.50:
- Net debit: $2.50 ($250 per contract)
- Max profit: (110 − 100) − 2.50 = $7.50 ($750)
- Max loss: $2.50 ($250)
- Breakeven: $102.50

### Strike Selection

- **Aggressive:** Buy ATM (50Δ), sell 30Δ — higher cost, higher max profit
- **Conservative:** Buy 40Δ, sell 20Δ — lower cost, lower max profit, higher probability of partial profit
- **Rule of thumb:** Collect 30–40% of spread width as debit (so $3–4 on a $10 wide spread)

---

## Bear Put Spread

### Setup

Buy a higher-strike put, sell a lower-strike put at the same expiration.

| Parameter | Detail |
|-----------|--------|
| Bias | Bearish (moderate move down) |
| Cost | Net debit |
| Max risk | Net debit paid |
| Max reward | Spread width − net debit |
| Breakeven at expiry | Higher strike − net debit |
| Best IV environment | Low-to-moderate IV |

### Payoff Example

Stock at $100. Buy 100 Put at $4.00, Sell 90 Put at $1.50:
- Net debit: $2.50 ($250 per contract)
- Max profit: (100 − 90) − 2.50 = $7.50 ($750)
- Max loss: $2.50
- Breakeven: $97.50

---

## Strike and Expiration Selection for Directional Trades

### Strike Selection

| Goal | Strike Choice | Delta Approx |
|------|--------------|-------------|
| Aggressive, high leverage | OTM (buy 30Δ) | 0.25–0.35 |
| Balanced, lower cost | Slight OTM (40Δ) | 0.35–0.45 |
| Conservative, ITM | ITM (70Δ) | 0.60–0.75 |

- **OTM options:** Cheap, high leverage, but require large moves. Most expire worthless.
- **ATM options:** Most time value, highest theta drag, good balance of cost and delta.
- **ITM options:** Expensive in dollar terms but low time value (mostly intrinsic); behave more like stock with limited theta decay.

### Expiration Selection

| Time Horizon of Thesis | Recommended DTE |
|----------------------|----------------|
| 1–2 week catalyst | 2–4 weeks (gives buffer beyond event) |
| 1 month view | 45–60 DTE |
| 2–3 month view | 60–90 DTE |
| 6+ month view | 90–180 DTE or LEAPS |

**Key rule:** Buy more time than you think you need. Options expire faster than expected. A 30-day option for a 3-week thesis has very little buffer — one delay and theta destroys the position. Give yourself at least 1.5× the expected time for the move.

### Common Mistakes in Directional Trades

1. **Buying too little time** — catalyst delayed, theta kills the position
2. **Buying in high IV** — stock moves the right way but IV crush offsets gains
3. **Choosing too far OTM** — requires an unrealistically large move to profit
4. **Not having a stop** — holding a long option to zero rather than cutting at 50% loss
5. **Over-concentrating in one expiration** — all positions expire in same month; correlated losses

---

## Long Call vs Long Stock Comparison

| Feature | Long Stock | Long Call |
|---------|-----------|-----------|
| Capital required | Full price × shares | Premium only |
| Max loss | Full stock price | Premium paid |
| Leverage | 1× | 5–20× (depending on strike) |
| Time decay | None | Yes, hurts the position |
| Dividends | Received | Not received |
| Best use | Long-term hold, income via CC | Short-term catalyst with defined risk |
