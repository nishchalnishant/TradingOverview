# Position Sizing and Max Loss

## Sizing by Max Loss

Options positions should be sized so that the **maximum possible loss** stays within a predetermined risk limit per trade — typically 1–2% of total account value.

### Formula

```
Max contracts = (Account × Risk %) / Max loss per contract

Example:
  Account = $50,000
  Risk per trade = 1% = $500
  Bull put spread: sell 95P/buy 90P for $1.50 credit on $5 wide spread
  Max loss per contract = ($5.00 − $1.50) × 100 = $350

  Max contracts = $500 / $350 = 1.4 → 1 contract
```

Never round up when the result is not a whole number — round down to stay within your risk limit.

### Risk % Guidelines

| Account size | Suggested risk per trade | Why |
|-------------|--------------------------|-----|
| < $25,000 | 1–2% (strict upper end) | Small accounts; a string of losses is devastating |
| $25,000–$100,000 | 1–2% | Standard professional range |
| > $100,000 | 0.5–1% | At scale, 1% is already a meaningful dollar amount |

Higher-volatility underlyings, wider spreads, or shorter-DTE positions may warrant the lower end of the range.

---

## Spread Width and Credit Received

The spread width determines your maximum loss and, combined with the credit collected, sets the return on capital.

### Key Calculations

```
Max loss = Spread width − Credit received (per share × 100 for dollar cost)
Max gain = Credit received
Return on capital (ROC) = Credit / Max loss
Breakeven = Short strike − Credit (for put spread) or + Credit (for call spread)
```

### Example Comparison: Narrow vs Wide Spread

| Structure | Short Strike | Long Strike | Credit | Width | Max Loss | ROC |
|-----------|-------------|------------|--------|-------|---------|-----|
| Narrow spread | 95P | 93P | $0.70 | $2.00 | $1.30 | 53.8% |
| Wide spread | 95P | 90P | $1.50 | $5.00 | $3.50 | 42.9% |

The narrow spread has a better ROC percentage but collects less absolute premium. The wide spread collects more absolute credit but has a higher dollar max loss.

**Practical rule:** Use $5-wide spreads as the default on stocks in the $50–$200 range; $10-wide on higher-priced stocks or index ETFs. Ensure credit is at least 30% of spread width — otherwise you are accepting high risk for too little reward.

---

## Naked vs Defined-Risk Structures

### Why Naked Short Options Are Dangerous

A naked short call or put has no protective wing. If the underlying makes a large adverse move, losses are unlimited (naked call) or extremely large (naked put down to zero).

| Structure | Max Loss | Example ($100 stock) |
|-----------|---------|---------------------|
| Short naked put | Strike × 100 − Credit | Short 90P for $2: max loss $8,800 |
| Bull put spread (90/85P) | Width − Credit | Short 90P/Long 85P for $1.50: max loss $350 |
| Short naked call | Unlimited | Short 110C for $2: unlimited loss |
| Bear call spread (110/115C) | Width − Credit | Short 110/Long 115C for $1.20: max loss $380 |

A gap-down of 20% on a naked short put at the 90 strike costs:
- Naked: (90 − 80) × 100 − $200 = $800 loss (4× the premium)
- Spread: max loss $350 regardless of how far the stock falls

For retail traders: defined-risk structures should be the default. Naked options are only appropriate when:
- Account is specifically approved for and can withstand the margin requirements
- Underlying is an index (less gap risk than single stocks)
- Position is small relative to account
- Clear exit plan is in place before trade entry

### Margin for Naked Options

Brokers require substantial margin for naked short options. The typical requirement:
- Naked short put: 20% of underlying price − out-of-the-money amount + premium received
- Naked short call: 20% of underlying price + premium received (for deep ITM, even more)

This margin is not your max loss — it is the capital your broker ties up. The actual max loss can far exceed the margin requirement.

---

## Portfolio Greeks Management

Managing individual positions is necessary but not sufficient. The entire portfolio has aggregate Greeks that determine how it responds to market moves.

### Portfolio-Level Delta

Total portfolio delta = sum of all position deltas.

```
Example:
  Position A: Long 2 calls, delta 0.50 each → +100 deltas
  Position B: Short 1 iron condor (long 10Δ put, short 25Δ put, short 25Δ call, long 10Δ call) → roughly 0 net delta
  Position C: Short 1 put, delta 0.30 → +30 deltas (short put = positive delta)
  
  Total portfolio delta: +130 deltas
  Equivalent to: long 130 shares of the underlying index/stock
```

If your maximum comfortable directional exposure is ±100 deltas (equivalent to 100 shares), the portfolio above has exceeded that limit. Hedge by:
- Selling some call spread to reduce positive delta
- Buying puts to add negative delta
- Closing the long calls partially

### Portfolio-Level Theta

Total daily theta = sum of all position thetas.

```
  Position A: Long calls, theta −$15/day
  Position B: Iron condor, theta +$40/day
  Position C: Short put, theta +$12/day

  Net portfolio theta: +$37/day
```

Positive portfolio theta means the book earns $37/day from time decay. Negative portfolio theta means you are paying $37/day in option time value.

**Target for income-focused portfolios:** Positive portfolio theta that represents 0.1–0.2% of account per day (e.g., $50–$100/day on a $50,000 account).

### Portfolio-Level Vega

Total vega = sensitivity to a 1% move in IV across all positions.

```
  If portfolio vega = −$200:
  A 5% rise in IV costs: 5 × $200 = $1,000
  A 5% fall in IV earns: 5 × $200 = $1,000
```

Short vol (income) portfolios have negative vega. An IV spike on a market correction can rapidly cause large losses even if the underlying doesn't move much. Limit negative portfolio vega to a level you can withstand during a VIX spike.

**Rule:** Negative portfolio vega should not exceed 2–3× your daily theta. This means a 1% IV move costs at most 2–3 days of theta — recoverable within a week of normal decay.

---

## Concentration Risk

### Sector Concentration

Options positions in the same sector are correlated. If you have:
- Short puts on AAPL, MSFT, GOOGL (all tech)
- All expire in the same month

A sector selloff hits all positions simultaneously. The correlation means your diversification is illusory.

**Rule:** Spread positions across at least 3–4 uncorrelated sectors or asset classes. Technology, healthcare, consumer staples, and commodities have historically lower cross-correlations.

### Expiration Concentration

Clustering all positions in the same expiration creates a "expiration event": at that one expiration, all positions close simultaneously, requiring maximum attention and creating correlated P&L.

**Rule:** Stagger expirations. Maintain positions across 3–4 different monthly expirations. When one expires, open the next to maintain the staggered structure.

### Single-Name Concentration

Don't allocate more than 10–15% of the portfolio's risk capital to a single stock. Single stocks can gap 20–50% on earnings, FDA results, or fraud revelations — moves that would cause maximum loss on almost any defined-risk structure, and catastrophic loss on naked positions.

---

## Summary: Risk Management Rules at a Glance

| Rule | Threshold |
|------|----------|
| Max loss per trade | 1–2% of account |
| Use defined risk | Always for single stocks; strongly preferred for indices |
| Min credit on spread | 30% of spread width |
| Profit target (short premium) | 50% of max credit |
| Loss limit (short premium) | 2× credit received |
| Max DTE at management | 21 DTE — close or roll |
| Portfolio delta | ±100–200 deltas (adjust for account size) |
| Vega/theta ratio | |Negative vega| ≤ 2–3× daily theta |
| Sector concentration | ≤ 25% of positions in one sector |
| Single-name concentration | ≤ 10–15% of risk capital per stock |
