# Section 1 — Foundations

The building blocks of options: what they are, how they are priced, and the mechanics every trader must internalize before placing a single trade.

---

## Contents

| Document | Topic |
|----------|-------|
| [Calls and Puts](calls-and-puts.md) | Contract mechanics, payoffs, ITM/ATM/OTM, premium components, exercise styles |
| [Option Pricing](option-pricing.md) | Black-Scholes, binomial model, pricing drivers, put-call parity |

---

## Key Takeaways

- An option is a **contract giving the buyer the right (not obligation)** to buy or sell an asset at a specified price before or at expiration.
- The **seller (writer)** of an option collects premium and takes on the obligation. The seller's risk can be large or unlimited depending on structure.
- Option premium has two components: **intrinsic value** (how far ITM) and **time value / extrinsic value** (everything else: time remaining, implied volatility, interest rates).
- **The Greeks** (covered in Section 2) quantify how the premium changes with price, time, and volatility — they are the primary tools for managing risk.
- Pricing models (Black-Scholes, binomial) give theoretical value; the **market price reflects supply, demand, and implied volatility**, which can deviate substantially from theoretical value.

---

## Why This Section Matters

Every options strategy — covered calls, spreads, straddles, iron condors — is built from long and short calls and puts. Misunderstanding the basics causes traders to:

- Underestimate time decay on long options
- Misjudge the breakeven of a position
- Confuse the obligation of a short option with the right of a long option
- Miss early assignment on short in-the-money options

---

## Quick Links

- Next: [02 — The Greeks](../02-greeks/README.md)
- [Strategies](../04-strategies/README.md)
- [Options Overview](../../README.md)
