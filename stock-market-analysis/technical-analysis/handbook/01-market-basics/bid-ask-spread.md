# Bid, Ask, and Spread

## Concept

- **Bid:** Highest price buyers are willing to pay.
- **Ask (Offer):** Lowest price sellers are willing to accept.
- **Spread:** Ask − Bid. It is the **immediate cost** of doing a round-trip trade (buy then sell at current quotes).

```
    ASK  $100.05  ← Sellers here
    ─────────────
    BID  $100.00  ← Buyers here
    ─────────────
    SPREAD = $0.05 (5 cents)
```

---

## Why Spread Exists

- **Market makers** need to profit (they buy at bid, sell at ask).
- **Risk:** They hold inventory; wider spread compensates in volatile or illiquid names.
- **Information:** In uncertain or news-driven conditions, spread often widens.

---

## Impact on Trading

| Factor | Effect on spread |
|--------|-------------------|
| High volume / liquidity | Tighter spread |
| Low volume / liquidity | Wider spread |
| News / volatility | Wider spread |
| Large cap, major FX | Tighter spread |
| Small cap, exotic FX, crypto | Wider spread |

---

## Slippage

- **Definition:** Your fill price is worse than the quoted bid/ask (e.g. you buy above the ask when using a market order).
- **Causes:** Lack of size at the quote, fast movement, or your order being large relative to available liquidity.
- **Mitigation:** Use limit orders when possible; reduce size in thin or fast markets.

---

## Chart Interpretation

- Spread is not drawn on standard price charts; you see it in the **order book** or **Level II**.
- **Widening spread** before news or into the close often signals uncertainty or lower liquidity—consider reducing size or waiting.

---

## Trading Psychology

- **Overtrading:** Paying the spread many times (e.g. scalping in wide-spread names) can erase edge; factor spread into your edge.
- **Patience:** Placing limit orders at the bid (buy) or ask (sell) can improve fill and save spread; accept that you might not get filled.

---

## Risk Management

- **Cost:** Assume you pay at least half the spread on entry and half on exit; ensure your strategy’s expected profit is well above this.
- **Stops:** In wide-spread instruments, place stops with the spread in mind so normal noise doesn’t stop you out.

---

*See also: [Order Types](order-types.md) | [Liquidity and Order Flow](liquidity-and-order-flow.md)*
