# Options Trading — Detailed Summary

A condensed overview of options trading as covered in this repository (concepts and book notes). For full book notes and strategy detail, see [Options Trading](https://github.com/nishchalnishant/TradingOverview/tree/main/stock-market-analysis/options-trading) and [Book Notes](https://github.com/nishchalnishant/TradingOverview/tree/main/stock-market-analysis/options-trading/book-notes).

---

## 1. What Are Options?

**Definition:** **Call** = right (not obligation for buyer) to **buy** the underlying at the **strike** by **expiration**. **Put** = right to **sell** at the strike by expiration. Buyer pays **premium**; seller receives premium and takes the other side of the obligation (if assigned).

**Key terms:**
- **Strike:** Price at which the option can be exercised.
- **Expiration:** Date after which the option expires (American = exercise any time before; European = only at expiration).
- **Premium:** Price paid/received for the option (intrinsic + time value).
- **In-the-money (ITM):** Call when underlying > strike; Put when underlying < strike. **At-the-money (ATM):** Underlying ≈ strike. **Out-of-the-money (OTM):** Call when underlying < strike; Put when underlying > strike.

---

## 2. Option Payoffs (Long vs Short)

**Long call:** Profit when underlying rises above strike + premium paid. Max loss = premium. Unlimited upside potential.

**Long put:** Profit when underlying falls below strike − premium paid. Max loss = premium. Max gain when underlying → 0.

**Short call:** Collect premium; max gain = premium. Loss when underlying rises (unlimited unless covered).

**Short put:** Collect premium; max gain = premium. Loss when underlying falls (down to zero).

**Rule of thumb:** Long options = **limited risk** (premium), **positive theta** (time decay hurts). Short options = **premium income**, **negative theta** (time decay helps), but **margin and assignment risk**.

---

## 3. The Greeks

| Greek | Measures | Practical use |
|-------|----------|----------------|
| **Delta** | Rate of change of option price vs underlying. Call 0–1; Put 0 to −1. | Approx. probability of ITM; hedge ratio (e.g. 50 delta ≈ 0.5 shares per contract). |
| **Gamma** | Rate of change of delta vs underlying. | High near ATM; short options = negative gamma (losses accelerate when wrong). |
| **Theta** | Time decay (option value loss per day). | Long options lose theta; short options gain theta. Manage holding period. |
| **Vega** | Sensitivity to implied volatility (IV). | Long options = long vega (benefit from IV rise); short options = short vega. |

**Simplified:** Delta = direction; Theta = time; Vega = volatility. Use Greeks to size, hedge, and choose expiration/strike.

---

## 4. Implied Volatility (IV) vs Historical Volatility (HV)

- **Historical volatility (HV):** Realized volatility of the underlying (e.g. annualized standard deviation of returns). Backward-looking.
- **Implied volatility (IV):** Volatility implied by option prices (e.g. from Black-Scholes). Forward-looking; reflects market expectation and supply/demand for options.
- **Use:** Sell premium (e.g. sell puts/calls or spreads) when IV is **high** (rich options); buy options when IV is **low** (cheap) if you expect a move. Compare IV to HV and to own estimate of future volatility.

---

## 5. Basic Strategies (Overview)

| Strategy | View | Max risk | Max reward | Typical use |
|----------|------|----------|------------|-------------|
| **Long call** | Bullish | Premium | Unlimited | Leveraged upside |
| **Long put** | Bearish | Premium | Strike − premium | Leveraged downside / hedge |
| **Covered call** | Neutral to bullish | Stock decline (minus call premium) | Premium + (cap − stock cost) | Income on owned stock |
| **Protective put** | Own stock, fear drop | Premium + (stock decline to strike) | Limits downside | Insurance |
| **Bull call spread** | Bullish | Net debit | (Spread width − debit) | Cheaper than long call; cap upside |
| **Bear put spread** | Bearish | Net debit | (Spread width − debit) | Cheaper than long put; cap upside |
| **Straddle** (long) | Big move either way | Debit | Large if move > debit | Volatility / event |
| **Strangle** (long) | Big move; cheaper than straddle | Debit | Large if move > debit | Volatility; lower cost |
| **Iron condor** | Range-bound | Width of one side − credit | Credit | Premium in sideways market |

---

## 6. Risk and Position Management

- **Assignment:** Short option can be assigned (call → sell stock; put → buy stock). Manage before expiration if you don’t want assignment (close or roll).
- **Margin:** Short options require margin. Naked short calls = very high risk; use spreads or covered structures to define risk.
- **Position sizing:** Size by **max loss** (e.g. spread width or premium paid). Don’t over-concentrate in single name or expiration.
- **Expiration:** Avoid holding short options through expiration unless you are prepared to be assigned or take delivery.

---

## 7. How Options Fit With TA and FA

- **FA:** Underlying selection (what to buy/sell). Options express that view (e.g. long call on undervalued stock) or hedge (e.g. protective put).
- **TA:** Timing (when to open/close). Enter options when TA suggests entry; choose expiration and strike based on expected move and time horizon. Use TA for stop/target on the underlying.
- **Combined:** FA for conviction; TA for entry/exit; options for leverage, income, or defined risk.

---

## 8. Book Notes in This Repo

- **Options as a Strategic Investment** — Full strategies and applications.
- **The Options Playbook** — Beginner-friendly playbook of strategies.
- **Trading Options Greeks** — Greeks in depth for risk and optimization.
- **Options Volatility and Pricing** — Pricing and volatility (Natenberg).
- **The Bible of Options Strategies** — 60+ strategies reference.
- **Option Volatility and Pricing Strategies** (Sinclair) — Quant/volatility focus.
- **Options Made Easy** — Basics for beginners.
- **The Complete Guide to Option Strategies** — Strategy reference.

**Links:** [Options Trading README](../stock-market-analysis/options-trading/README.md) | [Book Notes](../stock-market-analysis/options-trading/book-notes/README.md)
