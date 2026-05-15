# Options with Fundamental Analysis

Fundamental analysis determines which stocks deserve options exposure and at what valuation. Options amplify both gains and losses — putting that leverage on a fundamentally strong stock at a cheap valuation is structurally superior to speculating on weak or overvalued businesses.

---

## Using FA to Select the Underlying

The first question in any options trade should be: "Is this a stock I would want to own at the strike price?" This is especially true for:
- Cash-secured puts (you may be assigned)
- Covered calls (you already own it)
- Long-dated calls and LEAPS

### Quality Screen for Options Candidates

When selling puts or buying long-dated calls, prefer stocks that pass these fundamental criteria:

| Criterion | Why it matters for options |
|-----------|---------------------------|
| **Strong balance sheet** (low debt/equity, positive FCF) | Reduces bankruptcy risk below short put strike; option seller's nightmare is a stock going to zero |
| **Consistent earnings growth** | Reduces the probability of a large negative earnings surprise |
| **Wide economic moat** (durable competitive advantage) | Limits downside in prolonged downturns |
| **Reasonable valuation** (P/E, EV/EBITDA relative to growth) | Overvalued stocks are more vulnerable to multiple compression; avoid selling puts on frothy names |
| **Liquid options market** (tight bid-ask, high OI) | Reduces execution cost; essential for efficient entry and exit |
| **Predictable business** (not binary-event dependent) | Fewer catastrophic surprise events; short premium strategies work better |

**Avoid for income/short premium strategies:**
- Highly levered companies (debt/equity > 3×) — any recession or rate move creates outsized stock risk
- Biotech/clinical-stage companies — binary FDA events can gap stocks 50–80% overnight
- Commodity-sensitive single stocks — hard to model; volatility driven by unpredictable external factors
- Stocks trading at 50×+ earnings with no margin of safety — high valuation means high risk of re-rating

---

## Long-Dated Calls on Undervalued High-Quality Stocks (LEAPS)

LEAPS (Long-term Equity AnticiPation Securities) are options with expirations of 1–3 years. They combine the leverage of options with enough time to allow a fundamental thesis to play out.

### Why LEAPS Work for Fundamental Investors

- **Capital efficiency:** A LEAPS call on a $100 stock might cost $12–$15, vs $10,000 to own 100 shares. The call provides similar directional exposure per dollar invested.
- **Defined risk:** Maximum loss is the premium paid — a stock can go to zero without a margin call.
- **Theta is manageable:** With 1–2 years, daily theta is very low. You are not fighting aggressive decay.
- **Time for thesis to develop:** A value investing thesis may take 12–18 months to be recognized. A 30-day option gives no room for thesis development; a 2-year LEAPS does.

### LEAPS Selection Criteria

| Parameter | Recommendation |
|-----------|---------------|
| **DTE** | 12–24 months; longer is better for slow-burn theses |
| **Strike** | ATM to slight OTM (0.60–0.70 delta range); deeper OTM costs less but requires a larger move |
| **IV environment** | Buy LEAPS when IVR < 30% — cheap vol means cheap LEAPS |
| **Underlying** | Fundamentally strong, undervalued, durable business |

### LEAPS vs Long Stock: Risk-Adjusted Comparison

| Feature | Long Stock | LEAPS Call (60Δ, 18 months) |
|---------|-----------|------------------------------|
| Capital required | $100/share × 100 = $10,000 | ~$15/share × 100 = $1,500 |
| Max loss | $10,000 (stock to zero) | $1,500 (option expires worthless) |
| Leverage | 1× | ~6.7× per dollar invested |
| Theta cost | None | ~$0.03/day (low for LEAPS) |
| Dividends | Received | Not received |
| Upside at $130 | +$3,000 (+30%) | +$1,500 on $1,500 invested (+100%) |

**Key risk:** If the underlying falls significantly and stays down, the LEAPS expires worthless. With stock, you still own the asset. Only use LEAPS when you have strong fundamental conviction and the option was purchased cheaply (low IV).

### Rolling LEAPS

As the LEAPS approaches 6–9 months to expiry, it enters a zone of meaningfully accelerating theta. At this point, roll to a new LEAPS by:
1. Selling the current LEAPS (still has significant time value)
2. Buying a new LEAPS with 12–18 months remaining
3. This maintains continuous long exposure while resetting the theta clock

---

## Using Covered Calls on Long-Term Holdings to Enhance Yield

Covered calls are the most practical options strategy for fundamental buy-and-hold investors. They convert a portion of the stock's upside into immediate income.

### Systematic Covered Call Writing

1. Own 100 shares of a stock you want to hold long-term
2. Every 30–45 days, sell an OTM call (typically 20–30 delta) against those shares
3. Collect premium; if stock stays below strike, repeat
4. If stock surges past strike, shares are called away at the strike — still a profitable outcome

### Covered Call Returns: Realistic Expectations

| Stock IV | Strike delta | Approx. monthly premium | Annualized premium yield |
|----------|-------------|------------------------|--------------------------|
| 20% IV | 20Δ, 30 DTE | ~0.4–0.6% of stock price | ~5–7% |
| 30% IV | 20Δ, 30 DTE | ~0.7–1.0% | ~8–12% |
| 40% IV | 20Δ, 30 DTE | ~1.0–1.5% | ~12–18% |

These yields are in addition to stock appreciation up to the call strike. The trade-off: if the stock rallies above the strike, the position is capped and the shareholder misses excess upside.

### Covered Call Discipline Rules

- **Sell only on stocks you're comfortable owning long-term** — assignment means the stock gets sold; if you don't want to sell at the strike, don't sell the call.
- **Use OTM strikes** — selling ITM calls guarantees near-certain assignment and captures little upside. Standard practice: 20–30Δ.
- **Roll when challenged, not when threatened** — only roll when the stock is within a few percent of the strike; don't roll preemptively on a small move.
- **Take 50% profit** — if the call falls to 50% of premium collected, buy it back and sell a new one. Captures two premium cycles in the same time period.

---

## Earnings Plays: Positioning Before and After Earnings

Earnings announcements are the most common fundamental catalyst for options trades. IV is elevated pre-earnings (the market is uncertain) and collapses post-earnings (uncertainty resolved).

### Pre-Earnings Strategies

| Strategy | Approach | Best when |
|----------|----------|----------|
| **Earnings straddle/strangle** | Buy ATM straddle before earnings; sell after IV crush | Cheap IV relative to expected move; expect a large surprise |
| **Directional spread** | Buy debit spread toward the expected direction | High conviction on direction based on FA analysis |
| **Sell iron condor** | Sell strikes beyond the expected move range | High IV; believe market has overpriced the move |
| **Do nothing** | Stay flat through earnings on short-premium positions | Default when you have no edge on direction or magnitude |

### Computing the Expected Move

```
Expected move ≈ ATM Call price + ATM Put price (at front-month nearest to earnings)

Example: SPX earnings, ATM call $4.50 + ATM put $4.20 ≈ $8.70 expected move

If you think the stock moves more than $8.70 → buy the straddle
If you think the stock moves less than $8.70 → sell defined-risk condor
```

### Post-Earnings Strategies

After earnings, IV collapses and a new information set is available. FA informs what to do with the resulting position:

| Post-Earnings Situation | FA-Informed Action |
|------------------------|-------------------|
| Beat on revenue + guidance raised | Buy or hold calls; sell puts to acquire more stock if fundamentally compelling |
| Miss on revenue + guidance cut | Consider puts or close long exposure; reassess fundamental thesis |
| Beat on earnings but miss on revenue | Mixed signal; wait for management commentary; avoid adding new options exposure immediately |
| No surprise; stock flat | If IV has crushed and stock is range-bound, sell iron condor for the next month |

### Earnings Positioning Best Practices

- **Never hold naked short options over earnings** — a 20–40% gap happens multiple times per year in single stocks
- **Use iron condors if selling premium** — defined max loss prevents catastrophic losses on large gaps
- **Size down for earnings** — even defined-risk structures face their maximum loss on large moves; use 50% of normal position size
- **If trading pre-earnings, have a post-earnings exit plan** — don't hold long straddles after the catalyst; IV crush destroys value rapidly

---

## Hedging a Fundamental Long Thesis with Puts

A fundamental investor who is long a stock and confident in the business may still want to hedge against macro headwinds, market-wide selloffs, or near-term uncertainty.

### Protective Put as Insurance for a Long Thesis

- Buy a put that activates at a price that would represent a fundamental overreaction (below your estimate of intrinsic value)
- The put says: "If the stock falls to $X, I'm not sure the market is valuing it correctly and I want to preserve capital"

**Example:** Own stock at $100, fair value estimate = $90, "catastrophic scenario" floor = $75
- Don't need protection at $90 (still fair value, would add more)
- Do want protection at $75 (something is fundamentally wrong or market is in panic)
- Buy 75-strike puts as a tail hedge, not a directional bet

### Using Collars on Fundamental Long Positions

If a stock has run significantly above your estimate of fair value, a collar can lock in a large portion of the gain:

1. Own stock purchased at $60, now at $100
2. Estimate fair value at $95 — stock is slightly rich
3. Sell 110 Call (cap upside above fair value at a premium)
4. Use proceeds to buy 90 Put (protect the large gain)
5. Result: locked in a $90–$110 range at zero net cost

This is a tax-efficient way to protect an unrealized gain without triggering a taxable sale.

### Long-Term Macro Hedges

Fundamental investors with concentrated equity portfolios can use long-dated index puts or VIX calls as portfolio-level hedges:

| Hedge | Cost | When to initiate |
|-------|------|-----------------|
| 10–15% OTM SPX puts (6–12 month) | 1–1.5% of portfolio per year | When valuation of the market is stretched (Shiller CAPE > 30) |
| VIX calls (strike 25–30, 3 months) | Very cheap when VIX < 16 | When VIX is historically low; cheap tail hedge |
| 20% OTM SPX LEAPS puts | Very cheap; lottery ticket | Buy periodically during low-vol regimes as structural protection |

---

## Summary: FA-Options Integration Rules

| Rule | Detail |
|------|--------|
| Quality screen for short-premium | Sell puts/covered calls only on strong balance sheet, consistent FCF, reasonable valuation businesses |
| LEAPS for fundamental convictions | Use 12–24 month calls on undervalued quality stocks; buy in low-IV environments |
| Covered calls for yield enhancement | 20–30Δ monthly on existing long positions; take 50% profit and repeat |
| Earnings: know your edge first | Only trade earnings options with a specific view on direction or magnitude — don't trade for the sake of an event |
| Hedges at fundamental extremes | Buy index puts when valuations are stretched; buy tail hedges when VIX is very low |
| Never sell puts on binary-event stocks | Avoid biotech, early-stage companies, and leveraged commodities for short-premium strategies |
