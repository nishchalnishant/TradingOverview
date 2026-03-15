# Position Sizing and Risk Per Trade

## Concept

**Position sizing** is deciding **how many units** (shares, contracts, lots) to trade so that if the **stop is hit**, you lose a **fixed percentage** of your account (e.g. 1%). It ties **stop distance** (in price) to **dollar risk** and **account size**.

---

## Risk Per Trade

- **Rule of thumb:** Risk **0.5% to 2%** of account equity per trade. 1% is common. Never risk so much that 5–10 consecutive losses could wipe you out.
- **Formula (units):**
  - **Dollar risk** = Account × Risk%
  - **Risk per unit** = |Entry − Stop| (distance per share/contract/lot).
  - **Position size (units)** = Dollar risk / Risk per unit.

Example:
- Account = $50,000. Risk = 1%. Dollar risk = $500.
- Entry = $100, Stop = $97. Risk per share = $3.
- Shares = $500 / $3 ≈ **166 shares** (round down for safety).

---

## Formula Summary

```
Dollar Risk    = Account Size × Risk%
Risk Per Unit  = |Entry Price − Stop Price|
Position Size  = Dollar Risk / Risk Per Unit
```

For **leveraged** instruments (e.g. futures, forex): Risk per unit = (Entry − Stop) in **points/ticks** × point value. Same logic: Dollar risk / Risk per contract = number of contracts.

---

## Chart Interpretation

- **Wider stop** (e.g. below a swing low) → **smaller position size** for the same % risk. **Tighter stop** → larger position size. The **dollar** risk stays constant.
- **Never** fix position size first and then “see where the stop is”—that leads to variable (often too high) risk. **Always** define stop first, then size.

---

## Trading Psychology

- **Sticking to 1%:** After a loss, the urge to “make it back” by risking more is dangerous. Keep risk per trade **fixed**.
- **After a win:** Avoid increasing size because you “feel good”; keep the same risk% unless you have a deliberate rule (e.g. scale up only after N consecutive wins or new equity high).

---

## Risk Management

- **Max daily loss:** Some traders stop trading after losing e.g. 2–3% of account in a day. Prevents revenge trading and runaway losses.
- **Max open risk:** If you have 3 positions, each risking 1%, total open risk = 3%. Ensure you’re comfortable with that in a worst-case (all 3 stop out).

---

## Example (Forex)

- Account = $20,000. Risk = 1%. Dollar risk = $200.
- EUR/USD long. Entry = 1.1000, Stop = 1.0950. Risk = 50 pips.
- Pip value per lot = $10 (standard). Risk per 0.1 lot = 50 × $1 = $50.
- Lots = $200 / $50 = **0.4 lot** (or 4 mini lots).

---

*See also: [Risk Reward and Kelly](risk-reward-and-kelly.md) | [Revision: Risk Management Formula Sheet](../../../Revision/Risk_Management_Formula_Sheet.md)*
