# How Financial Markets Work

## Concept

Financial markets are **mechanisms for price discovery** and **transfer of risk and capital**. Buyers and sellers submit orders; the exchange (or dealer) matches them and publishes prices and volume. Prices move when the balance between buy and sell interest changes.

```
  BUYERS  <—— Orders ——>  EXCHANGE / MATCHING ENGINE  <—— Orders ——>  SELLERS
                              |
                    PRICE & VOLUME (tape)
```

---

## Core Mechanics

1. **Price discovery** — The market price is the level at which the last trade occurred and at which new orders can currently execute (bid/ask). Price is not inherently "fair value" — it is simply the current equilibrium between supply and demand.
2. **Liquidity** — The ability to buy or sell without moving the price much. More orders near the current price = more liquidity. Liquid markets (S&P 500, EUR/USD) have tight spreads and deep order books. Illiquid markets (small-cap stocks, exotic FX pairs) have wide spreads and thin books.
3. **Transparency** — In regulated markets, trades and often order books are visible (or summarized), so participants can see where price is and where interest sits. Some markets (over-the-counter bonds, OTC derivatives) are less transparent.

---

## Market Structure Types

| Market Type | How It Works | Examples |
|---|---|---|
| Centralized exchange | All orders route to a single matching engine; full transparency of trades | NYSE, CME, Binance |
| Electronic Communication Network (ECN) | Multiple participants quote; best bid/ask from all ECN participants aggregated | Forex ECN, US equity ECN |
| Over-the-counter (OTC) | Bilateral agreements between parties; no central matching; less transparent | OTC bonds, FX spot at banks, OTC derivatives |
| Dark pools | Private exchanges where institutional orders match without public pre-trade transparency | Most major banks operate dark pools for equity block trades |

---

## How Orders Move Price

Price moves because of **order flow imbalance**. When there are more aggressive buy orders than sell orders at the current level, the matching engine exhausts the available ask liquidity and price must move up to find the next sellers. The reverse is true for sell pressure.

```
Bid side (buyers)    Ask side (sellers)
   100 @ 50.00          200 @ 50.01
   300 @ 49.99          150 @ 50.02
   500 @ 49.98          400 @ 50.03
```

If a large market buy order arrives for 350 shares, it will:
1. Fill 200 @ 50.01 (exhausts all asks at 50.01)
2. Fill 150 @ 50.02 (exhausts all asks at 50.02)
3. Best ask is now 50.03 — price has moved up 2 cents.

This is how institutional orders move price and why large orders are often broken into smaller pieces (algorithmic execution like TWAP/VWAP) to reduce market impact.

---

## Market Participants and Their Goals

| Participant | Goal | Typical Behavior |
|---|---|---|
| Retail traders | Profit from price movements | Small size; react to indicators, news, patterns |
| Institutional investors (funds) | Long-term capital appreciation | Large size; methodical accumulation/distribution over days or weeks |
| Market makers | Earn bid-ask spread; provide liquidity | Post bids and asks simultaneously; delta-hedge; rarely directional |
| High-frequency traders (HFT) | Arbitrage, rebates, latency advantages | Tiny margin, enormous volume; add to liquidity in normal markets |
| Hedgers (corporates, banks) | Reduce risk from underlying exposure | Not seeking profit from the trade itself; e.g. airline hedging jet fuel |
| Central banks | Policy objectives (currency management, financial stability) | Rare but high-impact interventions; can overwhelm technical levels |

Understanding which participants dominate a given market helps interpret unusual moves. A sudden spike on no news in an illiquid market may be HFT arbitrage or a stop hunt; a steady, large-lot grind up in equities often reflects institutional accumulation.

---

## Chart Interpretation

- **Time and sales (tape):** Sequence of trades; large aggressive buys/sells show institutional or informed flow.
- **Order book (depth):** Stack of bid/ask orders; thick book near price suggests support/resistance and lower slippage.
- **Candles/OHLC:** Reflect the outcome of this process (open, high, low, close) over a period.
- **Volume:** The total contracts/shares traded in a period. High volume at a level confirms that many participants transacted there — it is likely a significant reference point. Low volume at a new high or low suggests weak conviction.

---

## Key Market Concepts for Traders

### Spread and Cost of Trading

The **bid-ask spread** is the minimum cost of a round trip (buy and sell). In liquid markets it may be 1–2 cents; in illiquid markets it can be 1–5% of price. Every market order pays this cost.

- For scalpers: spread is a major factor in strategy viability.
- For swing traders: spread is usually negligible relative to the target move.

### Gaps

When price opens at a level different from the prior close (equity markets) or jumps discontinuously (crypto, futures), a **gap** forms on the chart. Gaps occur because:
- Overnight news or earnings (equities).
- Weekend events (crypto, futures).
- Illiquid pre-market session with a large order.

Gaps often act as magnets — price tends to "fill" the gap, but not always and not immediately.

### Market Hours and Sessions

| Session | Hours (UTC) | Key Instruments |
|---|---|---|
| Asian | 23:00–08:00 | JPY pairs, AUD pairs, Nikkei, ASX |
| London | 07:00–16:00 | EUR/GBP pairs, FTSE, European equities |
| New York | 13:00–22:00 | US equities (NYSE/NASDAQ), USD pairs, S&P 500 futures |
| Overlap (London/NY) | 13:00–16:00 | Highest liquidity for FX; best execution conditions |

Crypto and some futures markets trade 24/7 but liquidity still clusters around these windows.

---

## Trading Psychology

- Accept that you cannot know every order; focus on **structure, volume, and price action**.
- Avoid assuming "someone is manipulating" on every adverse move; **liquidity and order flow** explain most short-term moves.
- The market does not know where your stop is — stop-outs at obvious levels are usually caused by the natural mechanics of liquidity sweeps, not targeted manipulation.

---

## Entry/Exit and Risk

- **Entry:** Use limit orders when you want a specific price; market orders when speed matters more than price.
- **Exit:** Define stops and targets in advance; use stop orders to automate risk control.
- **Risk:** In illiquid or fast markets, market orders can slip; size and order type matter significantly.
- **Slippage:** The difference between your expected fill price and actual fill. Budget for it in any backtest or live strategy, especially on market orders in fast-moving conditions.

---

## Example

**Scenario:** Stock opens with a gap. You want to buy on a pullback.

**Use:** Limit order at a support level (e.g., prior day's high or VWAP) instead of chasing with a market order. This ties execution to your plan and often improves average price. If price does not come back to your level, skip the trade — the gap-up entry on a market order guarantees a poor risk/reward.

---

*See also: [Types of Markets](types-of-markets.md) | [Order Types](order-types.md) | [Liquidity and Order Flow](liquidity-and-order-flow.md) | [Market Participants](market-participants.md)*
