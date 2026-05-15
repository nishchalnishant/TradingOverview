# Theta and Vega

## Theta (Θ) — Time Decay

### Definition

Theta measures the rate at which an option loses value as one day passes, all else equal. It is expressed in dollars (or dollars per 100-share contract) per calendar day.

```
Θ = Change in option price / Change in time (one day)
```

Theta is typically **negative for long options** (they lose value as time passes) and **positive for short options** (the seller receives that decay).

| Position | Theta sign | Daily effect |
|----------|-----------|--------------|
| Long call | Negative | Option loses value every day |
| Long put | Negative | Option loses value every day |
| Short call | Positive | Position gains value every day |
| Short put | Positive | Position gains value every day |

---

### Why Options Lose Value Over Time

An option's extrinsic value compensates the seller for the **uncertainty** that the option may expire ITM. As time passes, uncertainty shrinks — there are fewer remaining days for the stock to move. At expiration, there is no uncertainty left, so extrinsic value goes to zero.

This is irreversible. Time only moves forward. No matter how favorable volatility or price, every day that passes erodes the extrinsic value a long option holder paid.

---

### Theta Acceleration: Non-Linear Decay

Theta does not decay linearly. It accelerates as expiration approaches, particularly for ATM options.

```
Extrinsic value remaining (ATM option, approximation):
  
  DTE:   90    60    45    30    21    14     7     1
  Value: 100%  82%   71%   58%   48%   37%   27%   10%

Rate of decay accelerates in final 30 DTE.
```

The decay rate follows a square root of time relationship: value ∝ √(DTE). So the final 21 DTE decays as much as the preceding 69 DTE. This is the "theta sweet spot" that income traders target: sell with 30–45 DTE and buy back at 21 DTE to capture the fastest portion of decay without holding through the highest-gamma period at expiration week.

### ATM vs OTM Theta

- **ATM options** have the highest absolute theta (most extrinsic value to decay)
- **OTM options** have lower absolute theta but their extrinsic value is also lower, so the percentage decay can be high
- **ITM options** have less extrinsic value (mostly intrinsic), so lower theta

---

### Long Options: Theta as a Headwind

If you are long an option, you are **fighting time decay every day.** To be profitable:

- The underlying must move enough to overcome the daily theta drag
- Alternatively, implied volatility must rise enough to offset decay (long vega benefit)

A long call that costs $3.00 with 45 DTE and theta of −$0.06/day will lose approximately $2.70 in theta alone by expiration if nothing else changes. The stock must move significantly just to break even.

**Implication:** Only buy options when you have a specific, near-term catalyst or when IV is low enough that the option is cheap relative to expected moves.

---

### Short Options: Theta as an Ally

Selling options collects premium that decays toward zero as time passes. If the stock stays in a range, the seller profits as theta does the work.

**However:** Short theta comes with short gamma and short vega. A large stock move or IV spike can wipe out weeks of theta gains in a single day. Selling options is not "free money" — it is taking on tail risk in exchange for premium.

---

## Vega (ν) — Sensitivity to Implied Volatility

### Definition

Vega measures how much an option's price changes for a 1 percentage-point move in implied volatility.

```
ν = Change in option price / Change in IV (1%)
```

Vega is **always positive for long options** (calls and puts). A rise in IV increases option premiums; a fall in IV decreases them.

| Position | Vega sign | Effect of IV rise | Effect of IV fall |
|----------|-----------|-------------------|------------------|
| Long call | Positive | Gains value | Loses value |
| Long put | Positive | Gains value | Loses value |
| Short call | Negative | Loses value | Gains value |
| Short put | Negative | Loses value | Gains value |

---

### Vega Behavior

| Condition | Vega Level | Why |
|-----------|-----------|-----|
| **ATM options** | Highest | Small IV changes have maximum impact on extrinsic value |
| **Deep ITM/OTM** | Lower | Less extrinsic value to be affected |
| **Long-dated options (LEAPS)** | Highest | More time means IV compounds over more days |
| **Short-dated options** | Lower | Less time for IV to compound |

Vega increases with time to expiration. This means LEAPS (1–2 year options) have very high vega exposure — a 10-point IV move can shift a LEAPS position by hundreds of dollars per contract.

---

### Implied Volatility Rank (IVR) and Percentile

Raw IV numbers are meaningless without context. A stock with 30% IV might be cheap (if it normally trades at 50%) or expensive (if it normally trades at 20%).

**IV Rank (IVR):** Where current IV sits relative to its 52-week high and low.

```
IVR = (Current IV − 52-week IV Low) / (52-week IV High − 52-week IV Low) × 100
```

| IVR | Interpretation | Strategy bias |
|-----|---------------|--------------|
| > 50% | IV elevated vs recent history | Sell premium (credit spreads, short strangles) |
| 30–50% | Neutral | Context-dependent |
| < 30% | IV compressed | Buy premium (debit spreads, long options, straddles) |

**IV Percentile:** What percentage of days in the past year had IV lower than today. More robust than IVR because it is not dominated by a single spike.

---

### IV Crush Around Events

Implied volatility expands before known events (earnings, FDA decisions, FOMC meetings) because the market is uncertain about the outcome. After the event resolves, uncertainty collapses and IV drops sharply — this is **IV crush**.

```
Before earnings: IV = 60%  → option is expensive, vega is high
After earnings:  IV = 30%  → option loses half its time value immediately
```

**Key trap for buyers:** Even if the stock moves significantly on earnings, an options buyer can lose money because the IV crush destroys premium faster than the directional move adds value. This is called "buying the volatility expansion and getting crushed."

**Key opportunity for sellers:** Selling options before earnings (collecting elevated IV) and closing after the crush is a common strategy — but it requires **defined risk** (spread) to limit exposure to a large gap.

#### Rules Around Events

- Avoid buying single-leg options (long straddles included) unless the expected move clearly exceeds the options market's priced-in move
- Calculate the **expected move** from options: ≈ (ATM call price + ATM put price)
- If you sell before earnings, use a spread to limit gap risk — a naked short option can lose multiples of the premium collected on a large gap

---

### Managing Vega Exposure

**Portfolio vega** measures total sensitivity to IV across all positions. If your portfolio has high positive vega and IV drops, you take a loss on all positions simultaneously.

Strategies to manage vega:

| Method | Description |
|--------|-------------|
| **Spread structures** | Buying one option while selling another reduces net vega vs single-leg positions |
| **Mix long and short vol** | Balance some long-vol positions (debit spreads, long options) against short-vol positions |
| **Match DTE to IV environment** | In high IV, sell longer-dated options (high vega, collect more); in low IV, keep shorter-dated |
| **Close before events** | If holding short vega positions, close before earnings/FOMC to avoid IV spike risk |
| **Calendar spreads** | Sell near-term, buy longer-term — the spread is long net vega (long the vol in the back month) |

---

## The Theta-Vega Trade-off

Theta and vega are fundamentally in tension for short options positions:

- **Short options = positive theta, negative vega**
- Every day that passes, theta works in your favor
- But if IV spikes, vega works against you and can overwhelm many days of theta gain

A useful rule of thumb: an IV spike of 1 percentage point can erase approximately one day of theta. So a 20-point IV spike erases 20 days of theta gains at once. This is why short vol strategies require strict risk management and position sizing.

---

## Summary Table

| Greek | Sign (long option) | Highest when | Key rule |
|-------|--------------------|-------------|----------|
| **Theta** | Negative | ATM, short DTE | Sell options with 30–45 DTE; buy back at 21 DTE to ride fastest decay |
| **Vega** | Positive | ATM, long DTE | Use IVR to decide: sell vol when IVR > 50%, buy when < 30%; hedge before events |
