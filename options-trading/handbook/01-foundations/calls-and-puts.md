# Calls and Puts

## What Is an Option?

An option is a financial contract between a buyer and a seller. The buyer pays a **premium** to acquire a right; the seller receives that premium and accepts an **obligation**. Options trade on an underlying asset (stock, ETF, index, futures contract).

Two fundamental contract types:

| Type | Buyer's Right | Seller's Obligation | Buyer Profits When |
|------|--------------|--------------------|--------------------|
| **Call** | Buy the underlying at the strike price | Sell the underlying at the strike price if exercised | Underlying rises above breakeven |
| **Put** | Sell the underlying at the strike price | Buy the underlying at the strike price if exercised | Underlying falls below breakeven |

---

## Long vs Short (Buyer vs Seller)

**Long** means you paid premium and own the right. **Short** means you collected premium and carry the obligation.

| Position | Paid / Received | Right or Obligation | Max Risk | Max Reward |
|----------|----------------|---------------------|----------|------------|
| Long call | Paid premium | Right to buy | Premium paid | Unlimited (stock can rise indefinitely) |
| Short call | Received premium | Obligation to sell | Unlimited (uncovered) or width of spread | Premium received |
| Long put | Paid premium | Right to sell | Premium paid | Strike minus premium (stock can go to zero) |
| Short put | Received premium | Obligation to buy | Strike minus premium (stock to zero) | Premium received |

The seller's edge: premium collected immediately. The seller's risk: the premium received is far smaller than the maximum loss. This asymmetry is why **position sizing and structure (spreads) matter for sellers.**

---

## Payoff at Expiration

### Long Call
```
P&L
 |          /
 |         /
 |        /
─|───────●──────────────  underlying price
 |  loss │ breakeven = strike + premium
         strike
```
- **Breakeven:** Strike + premium paid
- **Max loss:** Premium paid (option expires worthless)
- **Max gain:** Unlimited

### Long Put
```
P&L
 \
  \
   \
────●────────────────────  underlying price
    │ breakeven = strike - premium
    strike
```
- **Breakeven:** Strike − premium paid
- **Max loss:** Premium paid
- **Max gain:** Strike − premium (if stock goes to zero)

### Short Call (naked)
- **Breakeven:** Strike + premium received
- **Max gain:** Premium received
- **Max loss:** Unlimited (stock can rise without bound)

### Short Put
- **Breakeven:** Strike − premium received
- **Max gain:** Premium received
- **Max loss:** Strike − premium received (stock falls to zero)

---

## Moneyness: ITM, ATM, OTM

Moneyness describes the relationship between the current stock price (S) and the option's strike price (K).

| Status | Call Condition | Put Condition | Has Intrinsic Value? |
|--------|---------------|--------------|----------------------|
| **In the Money (ITM)** | S > K | S < K | Yes |
| **At the Money (ATM)** | S ≈ K | S ≈ K | No (approximately) |
| **Out of the Money (OTM)** | S < K | S > K | No |

**Significance:**
- ITM options have **intrinsic value** and higher delta; they move more like the stock.
- ATM options have the **highest time value** and the highest gamma; they are most sensitive to small price moves.
- OTM options are **cheaper** but require a larger move to become profitable; they are purely extrinsic value.
- Deep ITM options behave almost like stock (delta near 1); deep OTM options behave almost like lottery tickets (delta near 0).

---

## Premium Components: Intrinsic Value + Extrinsic Value

**Option Premium = Intrinsic Value + Extrinsic (Time) Value**

### Intrinsic Value
The immediate exercise value. The amount by which the option is in the money.

- Call intrinsic value = max(S − K, 0)
- Put intrinsic value = max(K − S, 0)
- OTM and ATM options have **zero intrinsic value** — all premium is extrinsic.

### Extrinsic (Time) Value
Everything else in the premium above intrinsic value. Driven by:

| Driver | Effect on Extrinsic Value |
|--------|--------------------------|
| **Time to expiration** | More time → more extrinsic value. Decays to zero at expiry. |
| **Implied volatility (IV)** | Higher IV → more extrinsic value. Market expects larger moves. |
| **Interest rates** | Slight positive effect on calls, negative on puts (via cost of carry). |
| **Dividends** | Upcoming dividends reduce call value, increase put value. |

Extrinsic value is what option sellers are selling and what buyers must overcome to profit. At expiration, **all extrinsic value is zero** — an option is worth exactly its intrinsic value or nothing.

### Example

Stock at $105, Call strike $100, premium = $7:
- Intrinsic value = 105 − 100 = **$5**
- Extrinsic value = 7 − 5 = **$2**

Stock at $95, Call strike $100, premium = $2:
- Intrinsic value = max(95 − 100, 0) = **$0**
- Extrinsic value = **$2** (entirely time/vol premium)

---

## American vs European Exercise Style

| Feature | American | European |
|---------|----------|----------|
| **When can you exercise?** | Any time up to and including expiration | Only at expiration |
| **Where traded** | Equity options (AAPL, SPY individual stock options) | Index options (SPX, XSP), most European equity options |
| **Early assignment risk** | Yes — short options can be assigned early | No |
| **Premium** | Slightly higher (flexibility has value) | Slightly lower |

**Key practical point:** American-style short options carry **early assignment risk**, especially:
- Deep ITM short calls before ex-dividend date (holder exercises to capture the dividend)
- Deep ITM short puts when the time value is near zero (holder exercises to get cash)

European-style index options (e.g., SPX) are cash-settled and can never result in share delivery. Many traders prefer SPX for this reason when selling premium.

---

## Contract Specifications (Equity Options)

| Specification | Standard US Equity Option |
|--------------|--------------------------|
| Contract multiplier | 100 shares |
| Quoted price | Per share (multiply by 100 for actual cost) |
| Strike increments | $0.50, $1, $2.50, $5, or $10 depending on price |
| Expiration | Saturday after third Friday of expiration month (settlement Friday close) |
| Exercise | American style |

A call quoted at $2.50 costs **$250** to buy (2.50 × 100). Always compute the dollar cost, not just the per-share price, when sizing positions.
