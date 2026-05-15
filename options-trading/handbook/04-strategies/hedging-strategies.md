# Hedging Strategies

Hedging with options reduces the downside risk of an existing position or portfolio. Unlike directional strategies, the goal is not to profit from the hedge but to **limit the damage** when things go wrong. The cost of hedging is a drag on returns — treat it as insurance, not a profit center.

---

## Protective Put

### Setup

Own 100 shares of stock. Buy an OTM (or ATM) put to insure against a large decline.

```
P&L with protective put:
        /         ← stock alone
       /
──────●────────── (floor at strike - premium)
      |
      (put kicks in below strike)
```

| Parameter | Detail |
|-----------|--------|
| Bias | Long stock, but want downside protection |
| Cost | Put premium (ongoing insurance cost) |
| Max loss | (Stock price − Strike) + Premium paid (capped decline) |
| Max reward | Unlimited upside minus the premium paid |
| Breakeven | Stock purchase price + put premium |

### Payoff Example

Own stock at $100. Buy 90 Put for $2.00 (90 DTE).
- If stock falls to $75: loss on stock = $25; put gains $15 (90−75); net loss = $25 − $15 + $2 = **$12** (vs −$25 unhedged)
- If stock falls to $85: loss = $15 − $5 (put value) + $2 = **$12** (breakeven at $88)
- If stock rises to $115: gain = $15 − $2 premium cost = **$13 net** (vs $15 unhedged)

### Choosing Strike and Expiration

| Strike Choice | Protection | Cost | Use when |
|--------------|-----------|------|---------|
| ATM put | Full coverage from current level | Most expensive | Holding through a high-risk event; need tight protection |
| 5–10% OTM | Protects against moderate–severe drops | Moderate cost | Standard portfolio protection |
| 15–20% OTM | Tail risk protection only | Cheapest | Low-probability crash hedge; large portfolios |

| Expiration Choice | Cost | Use when |
|------------------|------|---------|
| 30–45 DTE | Cheapest per day, but must roll | Short-term hedge for known events |
| 90–180 DTE | Moderate cost, less rolling | Medium-term protection through uncertainty |
| LEAPS (1–2 yr) | Higher total cost, low per-day cost | Long-term structural hedge against a major position |

**Rolling rule:** As the put approaches expiry (21–30 DTE), buy the next expiration's put before the current one expires to maintain continuous coverage.

---

## Collar

### Setup

Own 100 shares. Buy an OTM put (downside protection) and sell an OTM call (fund the put premium).

```
         Sold call caps upside here
         ↓
─────────●──────── stock price (range-bound between put and call strikes)
         ●──────── 
         ↑
         Bought put floors downside here
```

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral; want to hold stock but limit risk |
| Net cost | Put premium − call premium (often near-zero or small debit/credit) |
| Max reward | Call strike − stock price + net credit (or − debit) |
| Max loss | Stock price − put strike + net debit (or − credit) |
| Breakeven | Stock price ± net premium |

### Zero-Cost Collar

When put and call premiums are roughly equal, the collar costs nothing upfront. The trade-off: you cap your upside at the call strike.

Example: Own stock at $100. Buy 90 Put at $2.50. Sell 110 Call at $2.50.
- Net cost: $0
- Protected range: $90 to $110
- Below $90: losses are capped
- Above $110: gains are capped (shares called away)

### When to Use Collars

- Large unrealized gain in a stock and you don't want to sell (would trigger taxes), but want to protect the position
- High IV environment (call premium offsets put cost effectively)
- Holding through an uncertain event but not wanting full unhedged exposure
- Estate planning / portfolio transition: protect large concentrated positions while arranging a sale over time

---

## Portfolio Hedging with Index Puts or VIX Calls

### SPX / SPY Puts

To hedge a diversified equity portfolio, buy put options on the S&P 500 index (SPX or SPY).

**Hedge ratio:** Determine how many puts you need to cover the portfolio.

```
Number of contracts = (Portfolio Value × Beta) / (Index Level × Multiplier)

Example:
  Portfolio = $500,000, Beta = 1.2
  SPY at $450 (multiplier = 100 shares = $45,000/contract)
  Contracts = ($500,000 × 1.2) / ($45,000) = 13.3 → buy 13 SPY puts
```

- Higher beta portfolio requires more contracts (amplified moves relative to index)
- Lower beta (defensive stocks, bonds, cash) requires fewer contracts

### Strike and DTE for Portfolio Hedges

| Hedge type | Strike | DTE | When to buy |
|-----------|--------|-----|------------|
| **Event hedge** | 5% OTM | 30–60 DTE | Before a specific risk event (election, FOMC) |
| **Ongoing tail hedge** | 15–20% OTM | 90–180 DTE | Always on; cheap protection against crashes |
| **Crash hedge** | 25–30% OTM LEAPS | 12–24 months | Low IV environment; very cheap; "lottery ticket" |

### VIX Calls as Hedges

When markets crash, VIX spikes. Buying VIX calls or VIX call spreads profits during market panic:

- VIX at 15 → VIX spikes to 40 in a crash → VIX calls gain dramatically
- Correlation: VIX is highly negatively correlated with S&P 500 returns
- **VIX calls are most effective as crash hedges when VIX is below 20** — they are cheap and provide convex payoffs during tail events

**Caution:** VIX options are European-style on forward VIX (the futures, not spot VIX). The strike in a VIX option corresponds to the VIX futures price, not spot VIX. Always check which expiration you need.

---

## Cost of Hedging: Premium Drag on Returns

Hedging is not free. Consistently buying puts or collars reduces portfolio returns over time because:
1. Most puts expire worthless (the stock doesn't fall to the strike)
2. Premium paid is the cost of insurance; like car insurance, most years you don't collect

**Historical cost:** Buying 5% OTM SPX puts monthly has historically cost 1–2% of portfolio value per year in premium. This drag must be weighed against the protection provided.

### Strategies to Reduce Hedge Cost

| Method | Description |
|--------|-------------|
| **Wider OTM strikes** | 15–20% OTM is much cheaper than 5% OTM; only protects against severe crashes |
| **Sell call spreads against puts** | Use proceeds of bear call spread to fund put purchase |
| **Collars** | Sell calls on holdings to offset put cost |
| **Buy puts only in high-risk periods** | Don't hedge all year; hedge before elections, Fed decisions, geopolitical stress |
| **Ratio spreads** | Buy 1× put at strike A, sell 2× puts at lower strike B; reduces or eliminates cost but adds tail risk below lower strike |

---

## Rolling Hedges

A hedge bought at one expiration must be extended (rolled) before it expires to maintain continuous coverage.

### When to Roll

- At **21–30 DTE** for short-dated hedges: at this point theta accelerates; the current put loses value rapidly with little time left
- When the hedge has moved significantly ITM (large loss has occurred): the hedge has done its job; consider closing and re-establishing OTM for continued protection

### How to Roll

1. **Close existing put**: sell the current put
2. **Open new put**: buy the next expiration's put at an appropriate strike
3. **Evaluate net cost**: often the ITM put has gained enough value that rolling is near-zero cost or even a credit

### Rolling Checklist

- [ ] Current hedge expires in < 30 days → begin rolling
- [ ] Check IV before rolling: if IV has spiked due to the event you hedged, the next put is now expensive → may roll to wider OTM or wait for IV to fall
- [ ] Recalculate hedge ratio: portfolio size, beta, or composition may have changed
- [ ] Consider whether the original hedging thesis still applies

---

## Summary: Hedging Strategy Quick Reference

| Strategy | Protects Against | Cost | Best For |
|----------|-----------------|------|---------|
| Protective put | Single stock decline | Moderate premium | Holding concentrated position |
| Collar | Single stock decline | Near-zero (call funds put) | Tax-sensitive hold; large unrealized gain |
| SPX/SPY puts | Broad market decline | Moderate | Diversified equity portfolio |
| VIX calls | Volatility spike (market crash) | Low (when VIX < 20) | Tail-risk hedge; portfolio diversification |
| Portfolio collar | Both single-name and market risk | Low-to-zero | Large multi-position book |
