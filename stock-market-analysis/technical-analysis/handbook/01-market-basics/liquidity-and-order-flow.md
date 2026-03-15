# Liquidity and Order Flow

## Concept

**Liquidity** is the ability to trade without moving price much. **Order flow** is the stream of buy and sell orders (and their execution). Price moves when order flow is **imbalanced**—more aggressive buyers than sellers (or vice versa).

---

## Liquidity

- **High liquidity:** Many orders near current price → tight spread, small slippage, easier to enter/exit.
- **Low liquidity:** Few orders → wide spread, large slippage, your order can move the market.

```
HIGH LIQUIDITY                    LOW LIQUIDITY
  Ask 100.02                        Ask 100.50
  Ask 100.01                        (gap)
  Bid 100.00  ← price                Bid 100.00  ← price
  Bid 99.99                          (gap)
  Bid 99.98                          Bid 99.20
```

---

## Order Flow

- **Aggressive buy:** Market buy or limit buy that lifts the ask → bullish pressure.
- **Aggressive sell:** Market sell or limit sell that hits the bid → bearish pressure.
- **Absorption:** Large passive orders (limits) that “absorb” aggressive flow; price holds until they are filled or pulled.

---

## Chart Interpretation

- **Volume bars:** High volume on up candles = buying pressure; on down candles = selling pressure.
- **Delta (volume):** In futures/options, volume delta (buy volume − sell volume) shows order flow imbalance.
- **Tape:** Large single trades or clusters of market orders in one direction suggest institutional or informed flow.

---

## Trading Psychology

- **Chasing:** Entering after a big move often means you’re buying from smarter money; wait for pullbacks or confirmation.
- **Thin markets:** In low liquidity, one large order can cause a spike; don’t assume it’s “the new trend” without confirmation.

---

## Entry/Exit and Risk

- **Entry:** Prefer entering where liquidity is present (e.g. at prior support/resistance or VWAP) so your order fills at reasonable price.
- **Exit:** In illiquid names, exit in smaller chunks or use limit orders to avoid moving price against yourself.
- **Risk:** Size position to liquidity; avoid taking large size in thin names.

---

## Example

- **Setup:** Stock holds above VWAP with repeated tests. Each test shows **absorption** (sellers unable to push price below).
- **Interpretation:** Buy-side order flow is dominant; consider longs on pullbacks to VWAP with a stop below.

---

*See also: [Bid, Ask, and Spread](bid-ask-spread.md) | [Market Participants](market-participants.md)*
