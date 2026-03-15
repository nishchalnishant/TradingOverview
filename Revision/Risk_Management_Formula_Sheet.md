# Risk Management Formula Sheet

Formulas and example calculations for position sizing and risk. Use for quick revision and live trading.

---

## Core Formulas

### 1. Dollar Risk

```
Dollar Risk = Account Size × Risk%
```

**Example:** Account = $40,000, Risk = 1%  
Dollar Risk = $40,000 × 0.01 = **$400**

---

### 2. Risk Per Unit (per share / per contract / per lot)

**Stocks (per share):**

```
Risk Per Share = |Entry Price − Stop Price|
```

**Example:** Entry = $50, Stop = $47  
Risk Per Share = |50 − 47| = **$3**

**Forex (per lot):**  
Risk in points × pip value per lot = risk per lot.  
Example: 50 pips × $10/pip (standard) = **$500** per standard lot.

**Futures:**  
Risk in points × point value = risk per contract.  
Example: 5 points × $20/point = **$100** per contract.

---

### 3. Position Size (units)

```
Position Size = Dollar Risk / Risk Per Unit
```

**Stocks example:**  
Dollar Risk = $400, Risk Per Share = $3  
Shares = $400 / $3 = **133 shares** (round down: 130)

**Forex example:**  
Dollar Risk = $400, Risk per 0.1 lot = $50  
Lots = $400 / $50 = **0.8 lot** (or 8 mini lots)

**Futures example:**  
Dollar Risk = $400, Risk per contract = $100  
Contracts = $400 / $100 = **4 contracts**

---

## Summary (Stocks)

| Step | Formula |
|------|---------|
| 1. Dollar risk | Account × Risk% |
| 2. Risk per share | \|Entry − Stop\| |
| 3. Shares | Dollar risk / Risk per share |

---

## Risk:Reward (R:R)

```
R:R = (Target − Entry) / (Entry − Stop)   for longs
R:R = (Entry − Target) / (Stop − Entry) for shorts
```

**Example (long):** Entry 100, Stop 97, Target 106  
R:R = (106 − 100) / (100 − 97) = 6/3 = **2** (1:2)

**Minimum:** Aim for **≥ 1:1.5** or **1:2**.

---

## Expectancy (per trade, in R)

If you risk 1R per trade:

```
Expectancy = (Win Rate × Avg Win in R) − (Loss Rate × Avg Loss in R)
```

With fixed 1R loss: Avg Loss in R = 1. So:

```
Expectancy = (Win Rate × Avg Win in R) − (1 − Win Rate)
```

**Example:** Win rate 50%, avg win 2R  
E = (0.5 × 2) − 0.5 = **0.5 R** per trade (positive edge).

---

## Kelly Criterion (optional)

**Full Kelly fraction:**

```
f* = (p × b − q) / b
```

- p = win rate, q = 1 − p  
- b = win/loss ratio (avg win / avg loss in same units)

**Example:** p = 0.5, b = 2  
f* = (0.5 × 2 − 0.5) / 2 = **0.25** (25% of bankroll—too high in practice)

**Use ¼ or ½ Kelly** for lower volatility, or ignore and use **fixed 0.5–2%** risk per trade.

---

## Max Drawdown (rough)

No exact formula. With **1% risk** and **50% win rate**, expect **strings of 5–10** losses.  
Rough guide: **10–20%** drawdown over a year is common. Size so you can **tolerate** that.

**Recovery:** After a 20% drawdown, you need **25%** return to break even (0.80 × 1.25 = 1.0).

---

## Quick Reference Table

| Item | Formula or value |
|------|-------------------|
| Risk per trade | 0.5–2% (e.g. 1%) |
| Dollar risk | Account × Risk% |
| Position size | Dollar risk / Risk per unit |
| Min R:R | 1:1.5 or 1:2 |
| Expectancy | (Win% × Avg win R) − (Loss% × 1) > 0 |
| Max daily loss | e.g. stop after 2% |
| Stop placement | Beyond structure/level (not arbitrary) |

---

*Full detail: [08 — Risk Management](stock-market-analysis/technical-analysis/handbook/08-risk-management/README.md).*
