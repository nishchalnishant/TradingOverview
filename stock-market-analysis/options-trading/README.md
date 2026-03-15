# Options trading

Options are **derivatives** that give the right (not obligation, for the buyer) to buy or sell an underlying asset at a set **strike** price by **expiration**. They are used for leverage, hedging, income, and expressing views on direction or volatility. This section points you to book notes and to a concise summary and tips.

---

## Core Concepts (Quick Reference)

### Definitions

- **Call:** Right to **buy** the underlying at the strike by expiration. Bullish view; max loss = premium; upside potentially unlimited.
- **Put:** Right to **sell** the underlying at the strike by expiration. Bearish view or hedge; max loss = premium; max gain when underlying → 0.
- **Strike:** Price at which the option can be exercised. **Expiration:** Date after which the option expires. **Premium:** Price paid/received (intrinsic + time value).
- **ITM / ATM / OTM:** In-the-money (call: underlying > strike; put: underlying < strike). At-the-money ≈ strike. Out-of-the-money = opposite of ITM.

### The Greeks

| Greek | Meaning | Practical use |
|-------|---------|----------------|
| **Delta** | Sensitivity to underlying price | Direction exposure; approx. hedge ratio |
| **Gamma** | Rate of change of delta | Acceleration of P&L; risk for short options |
| **Theta** | Time decay per day | Long options lose; short options gain |
| **Vega** | Sensitivity to implied volatility | Long options gain when IV rises; short lose |

### Implied Volatility (IV)

- IV is the **volatility implied by** option prices. High IV = expensive options (good to sell premium, costly to buy). Low IV = cheap options (good to buy). Compare to **historical volatility** and your view.
- **IV crush:** After events (e.g. earnings), IV often drops. Long options can lose value even with a favorable stock move.

### Basic Strategy Types

- **Directional:** Long call (bullish), long put (bearish), bull/bear spreads. Limited risk; defined reward for spreads.
- **Income / neutral:** Covered call, cash-secured put, iron condor, credit spreads. Collect premium; define max loss.
- **Volatility:** Long straddle/strangle (profit from big move); short straddle/strangle or iron condor (profit from range). Risk varies—short vol can be very risky.
- **Hedging:** Protective put (limit downside on stock); collar (cap upside and downside).

---

## How to Use This Section

1. **Book Notes** (below): In-depth notes from options classics—[Book notes README](book-notes/README.md). Start with beginner (e.g. Options Made Easy, Options Playbook) then move to Greeks and volatility (Trading Options Greeks, Options Volatility and Pricing).
2. **Summary:** Condensed overview of options (Greeks, strategies, risk, IV): [Summary — Options Trading Summary](../../Summary/Options_Trading_Summary.md).
3. **Tips and Tricks:** Practical tips on Greeks, expiration, IV, strategy choice, and risk: [Tips_and_Tricks — Options Trading](../../Tips_and_Tricks/Options_Trading_Tips.md).

---

## Book notes

Full descriptions and notes are in [Book notes README](book-notes/README.md). Summary:

1. **Options as a Strategic Investment** (McMillan) — Comprehensive strategies; classic for serious traders.
2. **The Options Playbook** (Overby) — Beginner-friendly; playbook format.
3. **Trading Options Greeks** (Passarelli) — Delta, Gamma, Theta, Vega; essential for advanced traders.
4. **Options Volatility and Pricing** (Natenberg) — Pricing, volatility, and strategies; highly respected.
5. **The Bible of Options Strategies** (Cohen) — 60+ strategies; quick reference.
6. **Option Volatility and Pricing Strategies** (Sinclair) — Quantitative and volatility focus.
7. **Options Made Easy** (Cohen) — Basics for beginners.

---

## Related in This Repo

- **Technical Analysis:** For *when* to enter/exit options (e.g. at support, after breakout), see [Technical Analysis Handbook](../technical-analysis/handbook/README.md).
- **Fundamental Analysis:** For *what* underlying to trade options on, see [Fundamental Analysis](../fundamental-analysis/README.md).
- **Master Summary:** [Summary/Master_Summary.md](../../Summary/Master_Summary.md) ties Options with TA and FA in one place.
