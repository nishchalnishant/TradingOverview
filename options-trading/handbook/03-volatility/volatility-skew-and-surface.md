# Volatility Skew and Surface

## What Is Volatility Skew?

Black-Scholes assumes a single constant volatility for all strikes and expirations. In reality, the implied volatility varies by strike. Plot IV against strike price and you get the **volatility smile** or **skew**.

**Volatility skew** (or smirk) describes the pattern where lower strikes (puts, downside) trade at higher IV than higher strikes (calls, upside) — a common feature in equity markets.

```
IV
 |
50|  *
45|    *
40|       *
35|            *
30|                  *  *  *
25|                           *  *
   └─────────────────────────────── Strike
  (lower strikes)          (higher strikes)
   OTM puts                 OTM calls
   (high IV)                (low IV)
```

This is also called the **put skew** or **negative skew** (left side is elevated).

---

## Why Puts Trade at Higher IV Than Calls

The skew is not an arbitrage — it reflects rational market behavior:

1. **Demand for downside protection:** Institutional investors (pension funds, mutual funds) constantly buy put options to hedge long equity portfolios. This demand drives up put premiums and therefore put IV.

2. **Supply asymmetry:** Far fewer participants systematically sell puts (absorbing the demand) compared to those who sell calls (covered call writers against long stock).

3. **Crash risk / fat tails:** The empirical distribution of equity returns has a heavier left tail (crashes) than a normal distribution implies. The market prices this by demanding higher IV for OTM puts.

4. **Leverage and liquidity concerns:** In a crash, leverage unwinds rapidly and liquidity disappears — the true tail risk is larger than the normal distribution suggests.

---

## Call Skew vs Put Skew

| Type | Description | When seen |
|------|-------------|-----------|
| **Put skew** (negative skew) | OTM puts have higher IV than OTM calls | Equity indices, large-cap stocks — nearly always |
| **Call skew** (positive skew) | OTM calls have higher IV than OTM puts | Commodities (oil supply shock), biotech (binary catalyst where upside is more uncertain), crypto |
| **Smile** | Both OTM puts and OTM calls have higher IV than ATM | FX markets; also individual stocks with binary events |

**Most common pattern in equities:** Negative skew (put skew). This is the baseline assumption.

---

## Measuring Skew

**25-delta skew:** The most widely quoted skew metric.

```
25Δ Skew = IV(25Δ put) − IV(25Δ call)
```

- Positive value (put IV > call IV) = standard equity skew
- Higher number = more skew (more demand for puts, or more crash fear)
- Negative value = call skew (calls more expensive than puts)

**Risk reversal price:** Selling a 25Δ put and buying a 25Δ call (or vice versa). Its premium reflects the skew.

---

## The Volatility Surface

The full **volatility surface** adds the expiration dimension: IV varies by both strike and time to expiration. It is a 3D surface.

```
            IV
            |
         60 |  *           (near-term event spike)
         50 |     *    *
         40 |        *      *   *
         30 |           *         *   *
            |_____________________________ Strike
           /
          / Time to expiration (DTE)
         /
```

Key features of the volatility surface:
- **Strike dimension (smile/skew):** Covered above
- **Time dimension (term structure):** How IV changes across expirations

---

## Term Structure: Contango vs Backwardation

**Term structure** is the shape of IV plotted across expiration dates for a fixed strike (typically ATM).

### Normal (Contango)

Near-term IV < longer-dated IV. The market is calm now but expects uncertainty will persist or increase in the future.

```
IV %
 |
 |                     *    *    *
 |           *    *
 |    *  *
 |
 └──────────────────────────────── DTE
  1w  2w  1m  2m  3m  6m  12m
```

Contango is the normal state in equity markets. It makes calendar spreads attractive (sell near-term cheap IV, benefit from term structure).

### Backwardation

Near-term IV > longer-dated IV. Acute stress or event: the market expects near-term turmoil but longer-term stability.

```
IV %
 |  *
 |     *
 |        *
 |           *    *    *
 |
 └──────────────────────────────── DTE
  1w  2w  1m  2m  3m  6m  12m
```

Backwardation is a sign of current market stress (e.g., VIX backwardation during March 2020 COVID crash). This is when short-dated options are most expensive — sellers should wait for stabilization before selling premium.

---

## VIX Term Structure

The VIX measures 30-day SPX IV. VIX futures trade at various expirations, creating their own term structure.

| VIX Futures Curve | Signal |
|-------------------|--------|
| Contango (normal) | Market calm; VIX futures roll down toward spot → short VIX strategies have positive roll |
| Flat | Mild uncertainty |
| Backwardation | Stress; near-term fear high; current spot VIX elevated |

**VIX futures roll yield:** When the curve is in contango and VIX is elevated, futures roll down toward spot. Products like UVXY and SVXY exploit this roll. Note: these products decay in both directions due to daily rebalancing and are not long-term holds.

---

## Trading Skew: Risk Reversals

A **risk reversal** is a position that simultaneously trades two sides of the skew:

- **Sell put, buy call** (same DTE): Synthetic long stock; sell the expensive put skew, buy the cheap call. Collect credit or pay small debit.
- **Buy put, sell call**: Synthetic short stock; buy downside protection using proceeds from selling upside.

### When to Trade Risk Reversals

| Setup | Action | Rationale |
|-------|--------|-----------|
| Skew very high, expect mean reversion | Sell put, buy call (for credit) | Selling the expensive vol, buying the cheap vol |
| Bullish bias + want to own protection | Sell OTM call, buy OTM put | Lock in upside cap but fund put hedge |
| Bearish, want cheap puts | Sell OTM call, buy OTM put | Use call premium to offset put cost |

The risk: skew can remain elevated for extended periods, especially in bear markets when institutional demand for puts is relentless.

---

## Practical Implications for Strategy Selection

| Skew Condition | Impact on Strategy |
|---------------|-------------------|
| **High put skew (normal)** | Bull put spreads are more expensive to buy but collect more premium as credit spreads; bear call spreads are cheaper to enter |
| **Call skew** | Unusual; suggests speculative demand for upside; calls are expensive relative to puts |
| **Steep term structure contango** | Calendar spreads work well; sell front-month, own back-month |
| **Backwardation** | Avoid short strangles/condors on near-term — near-term IV is elevated due to fear, not edge |
| **Flat term structure** | Neutral; no structural edge from term structure |

### Skew and Spread Pricing

The skew creates a systematic asymmetry in spread pricing:

- **Bull put spread** (sell higher-strike put, buy lower-strike put): The put you sell (higher-strike, more expensive due to skew) collects more premium than the put you buy (lower-strike, slightly lower IV). Skew is your friend.
- **Bear put spread** (buy higher-strike put, sell lower-strike put): The put you buy is relatively expensive; the one you sell is cheaper. Skew works against you — you pay more for the spread than a flat-vol model would suggest.
- **Iron condor:** The put side collects more premium than the call side for equidistant strikes from ATM — skew creates asymmetry. Adjust by placing the put spread further OTM to equalize premium collected.

---

## Summary

| Concept | Key Point |
|---------|-----------|
| **Volatility skew** | Puts have higher IV than calls in equities; reflects crash risk and hedging demand |
| **Volatility surface** | IV varies by strike and expiration simultaneously |
| **Contango** | Normal term structure; near-term < long-term IV; favor selling front-month |
| **Backwardation** | Stress state; near-term > long-term IV; avoid selling near-term naked premium |
| **Risk reversal** | Trade the skew directly: sell expensive side (usually puts), buy cheap side (usually calls) |
| **Strategy impact** | Skew makes bull put spreads better than bear call spreads as credit trades in equities |
