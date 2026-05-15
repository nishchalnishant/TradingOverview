# Exchanges and Market Sessions

## How Exchanges Operate

Exchanges provide:

- **Central limit order book (CLOB):** All limit orders are stored and matched by price-time (or similar) rules.
- **Trade reporting:** Executed trades are reported (price, size, time) so everyone sees the same tape.
- **Listing and rules:** Which instruments trade, trading hours, circuit breakers, and margin.

**Alternative:** In **dealer markets** (e.g. some FX, bonds), you trade with a dealer who quotes bid/ask; there is no single “exchange” order book.

---

## Market Sessions (24-Hour Cycle)

Global markets trade in overlapping **sessions**. Liquidity and volatility change by session.

```
        Sydney    Tokyo     London     New York
          |---------|---------|----------|----------|
  00:00    [====]
  08:00              [========]
  12:00                    [============]
  16:00                         [============]
  21:00                              [======]
          UTC (approx)
```

| Session | Approx. (UTC) | Traits |
|---------|----------------|--------|
| **Asian** | 00:00–09:00 | Often range-bound; JPY pairs active |
| **London** | 08:00–16:00 | High FX volume; European equities open |
| **New York** | 13:00–21:00 | High US volume; overlaps London = most FX volatility |
| **Overlap (London + NY)** | 13:00–16:00 | Highest liquidity and volatility in FX |

---

## Volatility Patterns

- **Open:** Session open often has a spike (orders pile up overnight; gaps in equities).
- **Mid-session:** Can trend or range depending on news and flow.
- **Close:** Often increased volume (rebalancing, EOD positioning); can see reversals or continuation.
- **Off-hours:** Lower liquidity → wider spreads and easier for one large order to move price.

---

## Chart Interpretation

- **Equities:** Mark open and close of the primary exchange; VWAP and session high/low matter for intraday.
- **Forex:** Mark Asian high/low, then London open, NY open; trade breakouts or mean reversion off these levels.
- **Crypto:** 24/7; “session” is more about when traditional markets are open (risk-on/risk-off) than a fixed open/close.

---

## Trading Psychology

- **FOMO at open:** First 15–30 minutes can be choppy; waiting for structure (e.g. first pullback, VWAP hold) often improves entries.
- **Session bias:** If you only trade one session, adapt your strategy to that session’s typical behavior (trend vs range).

---

## Risk Management

- **Gaps:** Equities can gap between close and next open; size or use stops that account for gap risk.
- **Thin hours:** Trade smaller size or avoid taking large risk when liquidity is low (e.g. late Friday FX, holiday sessions).

---

*See also: [Types of Markets](types-of-markets.md) | [Liquidity and Order Flow](liquidity-and-order-flow.md)*
