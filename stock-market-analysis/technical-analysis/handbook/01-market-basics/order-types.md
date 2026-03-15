# Order Types: Market, Limit, Stop

## Overview

Order type defines **when** and **at what price** your order becomes a trade. Using the right type improves execution and risk control.

| Type | Execution | When to use |
|------|-----------|-------------|
| **Market** | Immediate at best available price | Speed critical; liquid names |
| **Limit** | Only at your price or better | You want price control |
| **Stop (stop-market)** | Becomes market order when price hits level | Trigger exit/entry on break |
| **Stop-limit** | Becomes limit order when price hits level | Trigger + price control |

---

## Market Order

- **What:** “Buy/sell now at whatever price is available.”
- **Pros:** Fills immediately (in liquid markets).
- **Cons:** Slippage; in thin or fast markets you can get a bad price.
- **Use:** When you must get in or out (e.g. news, closing position) and accept the current spread and slippage.

---

## Limit Order

- **Buy limit:** Execute only at or below your limit price.
- **Sell limit:** Execute only at or above your limit price.
- **Pros:** Price certainty; can improve price by placing at bid/ask or inside the spread.
- **Cons:** May not fill if price never reaches your level.
- **Use:** Entries at support/resistance; exits at targets; illiquid or wide-spread names.

```
BUY LIMIT @ 99.50   →  Fills when price trades at or below 99.50
SELL LIMIT @ 101.00 →  Fills when price trades at or above 101.00
```

---

## Stop Order (Stop-Market)

- **Buy stop:** Placed above current price; when price **trades at or above** the stop level, order becomes a **market buy**.
- **Sell stop:** Placed below current price; when price **trades at or below** the stop level, order becomes a **market sell**.
- **Use:** Stop-loss (sell stop below position); breakout entry (buy stop above resistance).
- **Risk:** In gaps or fast moves, the **fill can be far from the stop level** (slippage).

---

## Stop-Limit Order

- **What:** When price hits the stop level, a **limit** order is submitted (not market).
- **Pros:** Caps worst fill price (your limit).
- **Cons:** In a fast move, price may never trade at your limit → **no fill** (you stay in a losing position if used as stop-loss).
- **Use:** When you want a trigger plus price control and accept the risk of non-fill.

---

## Chart Interpretation

- **Support/resistance:** Limit orders often cluster there; breakouts can be accelerated when buy/sell stops are triggered above/below.
- **Stop hunts:** Price may briefly sweep stops below support (or above resistance) then reverse—part of why confirmation (e.g. close beyond level) matters.

---

## Trading Psychology

- **Stops:** Use stop orders to **enforce** exit; avoids “I’ll get out in a minute” and then holding into a larger loss.
- **Limits:** Reduces regret from bad fills but can cause regret from missed fills; balance with your strategy and timeframe.

---

## Risk Management

- **Stop placement:** Place stops where the **setup is invalidated** (e.g. below structure), not arbitrarily; avoid too-tight stops in volatile names.
- **Position size:** With stop orders, size so that the distance from entry to stop × size = your **max risk per trade** (e.g. 1% of account).

---

*See also: [Bid, Ask, and Spread](bid-ask-spread.md) | [08 — Risk Management](../08-risk-management/README.md)*
