# Delta and Gamma

## Delta (Δ)

### Definition

Delta measures how much an option's price changes for a $1 move in the underlying asset.

```
Δ = Change in option price / Change in underlying price
```

| Option Type | Delta Range | Interpretation |
|-------------|------------|----------------|
| Long call | 0 to +1 | Gains value as stock rises |
| Short call | −1 to 0 | Loses value as stock rises |
| Long put | −1 to 0 | Gains value as stock falls |
| Short put | 0 to +1 | Loses value as stock falls |

A call with delta 0.50 gains approximately $0.50 for every $1 the stock rises (and the position is for 1 contract = 100 shares, so $50 per contract).

---

### Delta as Hedge Ratio

Delta tells you how many shares of stock are equivalent to your option position.

- Long 1 call with delta 0.50 → behaves like **owning 50 shares**
- Long 1 put with delta −0.30 → behaves like **short 30 shares**

**Delta-neutral hedging:** To neutralize directional exposure, you offset the option delta with stock or other options.

Example: Short 1 ATM call (delta −0.50 × 100 = −50 deltas). To delta-hedge, buy 50 shares. Now the portfolio is delta-neutral — small moves up or down do not affect P&L (until gamma changes the delta).

---

### Delta as Approximate Probability ITM

Delta is also a rough proxy for the probability that an option expires in the money (under the risk-neutral measure).

| Delta | Approximate Prob. ITM |
|-------|-----------------------|
| 0.70 | ~70% |
| 0.50 | ~50% (ATM) |
| 0.30 | ~30% |
| 0.16 | ~16% (1 SD OTM) |
| 0.05 | ~5% (deep OTM) |

This is not exact — it ignores the difference between N(d1) and N(d2) in BSM, and real distributions have fat tails. But it is useful for thinking about probability of profit on short options.

---

### How Delta Changes

Delta is not static. It shifts as the underlying moves, time passes, and implied volatility changes.

| Factor | Effect on Call Delta | Intuition |
|--------|---------------------|-----------|
| Stock rises | Increases toward 1 | Option goes further ITM |
| Stock falls | Decreases toward 0 | Option goes further OTM |
| Time passes | ATM delta stays ~0.50; OTM delta falls toward 0 | Less uncertainty near expiry |
| IV rises | OTM deltas increase slightly; ITM deltas decrease slightly | Fatter tails mean more probability of ITM |
| IV falls | OTM deltas decrease; deep ITM increase | Tighter distribution |

---

## Gamma (Γ)

### Definition

Gamma measures how much delta changes for a $1 move in the underlying.

```
Γ = Change in delta / Change in underlying price
```

Gamma is always **positive for long options** and **negative for short options**, regardless of call or put.

- Long call: positive gamma — as the stock rises, delta accelerates from 0.50 toward 1.0
- Short call: negative gamma — as the stock rises, you become more short delta (losing more)

---

### Gamma Behavior

| Condition | Gamma Level | Why |
|-----------|------------|-----|
| **ATM options** | Highest | Small moves push the option in or out of the money; delta changes most |
| **Deep ITM or OTM** | Low | Delta is already near 1 or 0; further moves change it little |
| **Short-dated options (< 14 DTE)** | Very high for ATM | Only days left; a move quickly turns ATM into ITM/OTM |
| **Long-dated options (LEAPS)** | Low | Many days remain; a single move matters less to probability |

This is the core risk of **selling short-dated ATM options**: gamma is highest, so an adverse move rapidly changes your delta exposure.

---

### Gamma Scalping

Gamma scalping (delta-hedging a long gamma position) is a way to monetize realized volatility.

1. Buy an ATM straddle (long gamma, short theta)
2. Delta-hedge to stay neutral: as stock rises, delta goes positive → sell stock; as stock falls, delta goes negative → buy stock
3. Each hedge "locks in" a profit from the move
4. Net P&L = profits from scalping − theta paid

**You profit if realized volatility > implied volatility.** If the stock moves more than IV predicted, your scalping profits exceed your theta cost. If realized vol < IV, theta bleeds you out.

Gamma scalping is essentially making a **bet on realized volatility** while keeping direction neutral.

---

### Short Gamma Risk

Short gamma is the risk borne by option sellers. It means:

- As the stock moves against you, your delta exposure **increases** in the wrong direction
- A short call starts as slightly short delta; if the stock rallies 10%, delta may go from −0.30 to −0.80, dramatically increasing loss
- Losses accelerate as the underlying moves further against the position

This is why **stops, position size limits, and spread structures** are non-negotiable for short options positions. A naked short option has theoretically unlimited loss because gamma keeps increasing your exposure as the underlying moves.

**Short gamma + low theta = worst combination.** This happens when you sell cheap OTM options with little time left — IV may be low (small premium collected) but gamma risk is high for ATM strikes. Always verify the premium collected justifies the gamma risk.

---

## Practical Uses: Delta and Gamma in Trading

### Position Sizing

- Use delta to compute **equivalent share exposure** per option contract
- Limit total portfolio delta to a maximum directional exposure (e.g., ±200 deltas = equivalent of long/short 200 shares)

### Directional Trade Management

- Monitor delta as your trade moves ITM or OTM
- An OTM call that was 0.25 delta when purchased may become 0.70 delta if the stock rallies sharply — at that point, the option behaves like holding 70 shares, far more than intended
- Consider taking partial profits or rolling to a higher strike to reduce delta

### Hedging

- Delta-hedge a large options position by buying/selling the underlying to neutralize direction
- Re-hedge at regular intervals (daily, at a delta threshold) — gamma ensures the hedge drifts

### Gamma-Adjusted Strike Selection

- When selling options for income, choose strikes with low gamma (further OTM or longer-dated) to reduce the speed at which position turns against you if the stock moves
- 30-delta strikes are a common starting point: enough premium to be worthwhile, low enough gamma to give reaction time

---

## Summary Table

| Greek | Call | Put | Highest when | Practical rule |
|-------|------|-----|-------------|----------------|
| **Delta** | 0 to +1 | 0 to −1 | Deep ITM | Use as equivalent share count for sizing |
| **Gamma** | Always + (long) | Always + (long) | ATM, short DTE | Short gamma risk spikes near expiry; don't sell cheap short-dated ATM options naked |
