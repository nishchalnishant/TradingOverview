# Section 5 — Risk Management

Options amplify both gains and losses. Without disciplined risk management, even correct volatility and directional analysis can result in account blow-ups. This section covers position sizing, portfolio-level Greeks, assignment mechanics, and the practical rules for managing positions through their lifecycle.

---

## Contents

| Document | Topic |
|----------|-------|
| [Position Sizing and Max Loss](position-sizing-and-max-loss.md) | Sizing by max loss, spread structures, portfolio Greeks, concentration risk |
| [Assignment and Expiration](assignment-and-expiration.md) | Assignment mechanics, early exercise, rolling, expiration management |

---

## Core Risk Rules

1. **Never risk more than 1–2% of account on a single trade.** For defined-risk structures, this means max loss ≤ 1–2% of account value.

2. **Use defined-risk structures.** Credit spreads, iron condors, and debit spreads cap your loss. Naked short options can lose multiples of the premium collected in a single day.

3. **Know your Greeks at the portfolio level.** Each position adds or subtracts delta, gamma, theta, and vega from the total book. Manage the aggregate, not just individual positions.

4. **Manage at 21 DTE.** At 21 days to expiration, gamma risk spikes for short options. Close or roll before entering this danger zone.

5. **Take profits at 50%.** Closing a short premium position at 50% of max profit locks in most of the expected gain while eliminating the remaining time and gamma risk. The remaining 50% of potential gain requires 100% of the time and all the tail risk.

6. **Never let a short options loss become catastrophic.** If a position reaches 2× the premium collected as a loss, close it. A $100 credit turning into a $200 loss is expected occasionally; let it become $500 is a discipline failure.

---

## Quick Links

- Prev: [04 — Strategies](../04-strategies/README.md)
- Next: [06 — Combining with TA & FA](../06-combining-with-ta-and-fa/README.md)
- [Options Overview](../../README.md)
