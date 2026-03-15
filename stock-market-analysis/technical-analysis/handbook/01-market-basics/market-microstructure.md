# Market Microstructure Basics

## Concept

**Market microstructure** is the study of **how orders become trades**: matching rules, latency, fees, and how these affect price formation and liquidity.

---

## Key Elements

1. **Matching engine:** Matches buy and sell orders (price-time priority, or pro-rata, etc.).
2. **Latency:** Time from order submission to execution; matters for HFT and scalping.
3. **Fees and rebates:** Exchanges charge (or pay) for taking vs providing liquidity; affects optimal order type.
4. **Order types:** Market, limit, stop, IOC, FOK, etc.—each has a different impact on execution and queue.

---

## Price-Time Priority

- Orders at the **best price** execute first.
- At the same price, **earlier** orders execute first (queue).
- So: limit orders at the best bid/ask join the queue; market orders “take” from the opposite side and get immediate fill (at that price or worse).

---

## Implications for Traders

- **Retail (slower):** You rarely “win” the queue; your edge is in **strategy and risk**, not speed. Use limit orders to avoid paying the spread when possible.
- **Liquidity:** In stress, market makers may pull quotes or widen spread; expect worse execution and possible gaps.
- **Slippage:** Large market orders walk the book (consume multiple price levels); execution price can be worse than the best quote.

---

## Chart Interpretation

- Microstructure shows up as **short-term noise**: wicks, rapid reversals, and failed breakouts as stops are run and liquidity is tested.
- **Volume profile** and **time & sales** reflect the outcome of matching (who traded, at what price, how much).

---

## Trading Psychology

- Don’t blame “algos” for every adverse tick; much of it is **normal** order flow and liquidity.
- Accept that you cannot control execution tick-by-tick; focus on **setup, size, and risk**.

---

## Risk Management

- In **fast or thin** markets, reduce size or use limit orders to cap execution risk.
- **Gaps:** Outside regular hours or across sessions, matching may be thin; avoid oversized exposure into known risk events.

---

*See also: [How Exchanges Operate](exchanges-and-sessions.md#how-exchanges-operate) | [Order Types](order-types.md)*
