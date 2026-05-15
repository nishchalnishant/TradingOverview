# Section 4 — Strategies

Options strategies can be grouped into four broad categories based on their primary objective: directional, income/neutral, volatility, and hedging. Each category has different risk/reward profiles, optimal IV environments, and management approaches.

---

## Contents

| Document | Topic |
|----------|-------|
| [Directional Strategies](directional-strategies.md) | Long calls/puts, bull/bear spreads, strike and expiration selection |
| [Income and Neutral Strategies](income-and-neutral-strategies.md) | Covered calls, CSPs, credit spreads, iron condors, iron butterflies |
| [Volatility Strategies](volatility-strategies.md) | Straddles, strangles, short strangles, calendar spreads |
| [Hedging Strategies](hedging-strategies.md) | Protective puts, collars, portfolio hedging with index options |

---

## Strategy Category Overview

| Category | Directional Bias | IV Environment | Primary Edge |
|----------|-----------------|----------------|-------------|
| **Directional** | Bullish or bearish | Low-moderate IV | Right on direction + move exceeds premium paid |
| **Income / Neutral** | Neutral to slight bias | High IV | Sell overpriced premium; theta decay |
| **Volatility** | No directional view (long vol) or neutral (short vol) | Low IV (buy vol) / High IV (sell vol) | Realized vol > IV (long) or IV > realized vol (short) |
| **Hedging** | Protecting existing position | Willing to pay for insurance | Limiting downside risk; cost is drag on returns |

---

## Choosing the Right Strategy

Use this decision tree as a starting point:

1. **Do you have a directional view?**
   - Yes, strong conviction + specific catalyst → directional (long call/put, vertical spread)
   - No strong direction → income/neutral (iron condor, short strangle) or volatility (straddle if pre-event)

2. **What is the IV environment?**
   - IVR > 50% → Prefer selling premium (credit spreads, iron condors, covered calls)
   - IVR < 30% → Prefer buying premium (debit spreads, long options)
   - IVR 30–50% → Spreads neutral; defined risk on either side

3. **Do you need to protect an existing position?**
   → Hedging strategies (protective put, collar)

4. **Is there a binary event (earnings, FDA)?**
   → Defined-risk structures only; never naked short options around events

---

## Quick Reference: Strategy Risk/Reward

| Strategy | Max Risk | Max Reward | Best in |
|----------|---------|-----------|---------|
| Long call | Premium paid | Unlimited | Low IV, bullish |
| Long put | Premium paid | Strike − premium | Low IV, bearish |
| Bull call spread | Debit paid | Spread width − debit | Low-mid IV, bullish |
| Bear put spread | Debit paid | Spread width − debit | Low-mid IV, bearish |
| Covered call | Stock cost − premium | Strike − cost basis + premium | Any IV, neutral-bullish |
| Cash-secured put | Strike − premium | Premium received | High IV, neutral-bullish |
| Bull put spread | Spread width − credit | Credit received | High IV, neutral-bullish |
| Bear call spread | Spread width − credit | Credit received | High IV, neutral-bearish |
| Iron condor | Spread width − credit | Credit received | High IV, neutral |
| Long straddle | Total premium | Unlimited | Low IV, pre-event |
| Short strangle | Unlimited (naked) | Premium received | High IV, neutral |
| Protective put | Premium paid | Unlimited (from stock) | Any IV, hedging |

---

## Quick Links

- Prev: [03 — Volatility](../03-volatility/README.md)
- Next: [05 — Risk Management](../05-risk-management/README.md)
- [Options Overview](../../README.md)
