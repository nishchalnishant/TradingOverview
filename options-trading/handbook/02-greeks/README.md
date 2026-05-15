# Section 2 — The Greeks

The Greeks quantify how an option's price changes in response to changes in market conditions. They are the primary tools for measuring, understanding, and managing options risk.

---

## Contents

| Document | Topic |
|----------|-------|
| [Delta and Gamma](delta-and-gamma.md) | Directional sensitivity, rate of change of delta, hedging, gamma scalping |
| [Theta and Vega](theta-and-vega.md) | Time decay, IV sensitivity, IV rank, IV crush, managing vol exposure |

---

## The Core Greeks at a Glance

| Greek | Measures | Long option effect | Short option effect |
|-------|----------|-------------------|---------------------|
| **Delta (Δ)** | Price sensitivity to $1 move in underlying | Positive for calls, negative for puts | Reversed |
| **Gamma (Γ)** | Rate of change of delta | Always positive (long gamma) | Always negative (short gamma) |
| **Theta (Θ)** | Daily time decay ($ per day) | Negative (time is enemy) | Positive (time is ally) |
| **Vega (ν)** | Price sensitivity to 1% move in IV | Positive (benefit from IV rise) | Negative (hurt by IV rise) |
| **Rho (ρ)** | Price sensitivity to 1% move in interest rates | Minor factor for most trades | Minor factor |

---

## Key Relationships

- **Delta and gamma** are about directional exposure and how that exposure changes.
- **Theta and vega** are the two sides of the same coin: every day of time decay works for sellers (positive theta), but sellers are also short vega and hurt by volatility spikes.
- Long options: long gamma, short theta, long vega. These forces compete. A position makes money from large moves (gamma) but loses money daily (theta).
- Short options: short gamma, long theta, short vega. Collect time decay daily, but vulnerable to big moves and IV spikes.

---

## Why the Greeks Matter Practically

- You cannot manage a multi-position book by tracking individual P&L only. Portfolio-level delta tells you directional bias; portfolio vega tells you IV exposure; portfolio theta tells you daily decay income or cost.
- Professional options traders **manage Greeks**, not just individual trades.

---

## Quick Links

- Prev: [01 — Foundations](../01-foundations/README.md)
- Next: [03 — Volatility](../03-volatility/README.md)
- [Strategies](../04-strategies/README.md)
