# Options Trading — Tips and Tricks

Practical tips for Greeks, strategy choice, expiration, implied volatility, risk, and assignment. Use with the [Options Trading](https://github.com/nishchalnishant/TradingOverview/tree/main/stock-market-analysis/options-trading) and [Book Notes](https://github.com/nishchalnishant/TradingOverview/tree/main/stock-market-analysis/options-trading/book-notes) content.

---

## 1. Greeks in Practice

- **Delta as probability (rough):** 50 delta ≈ 50% probability of finishing ITM (simplified). Use delta to **size** (e.g. 30-delta call ≈ 0.3 shares per contract for directional exposure) and to **approximate** P&L for small moves (e.g. $1 move in stock ≈ $0.30 per 30-delta option).
- **Theta:** Long options **lose** value every day (negative theta). Short options **gain** (positive theta). Don’t buy long-dated options “to hold forever”—decide on a horizon and choose expiration accordingly. Close or roll before theta accelerates (e.g. last 30 days).
- **Vega:** When **IV is high** (e.g. before earnings), long options are expensive and short options are attractive (if you’re right on direction or range). When **IV is low**, buying options is cheaper; selling premium pays less. Compare current IV to **historical** and to your view.
- **Gamma risk:** **Short** options (especially naked or large size) have **negative gamma**: when the underlying moves against you, losses accelerate. Define risk with **spreads** or **position size**; avoid large naked short gamma.

---

## 2. Choosing Expiration and Strike

- **Time horizon:** Match **expiration** to your view. Short-term move (e.g. earnings) → near-term or weekly. Multi-month view → 3–6+ months out so theta doesn’t kill you. Avoid buying weekly options “for a quick trade” unless you’re very confident—decay is brutal.
- **Strike choice:** **ATM** = max sensitivity (delta, gamma). **OTM** = cheaper, higher leverage but lower delta; need bigger move. **ITM** = more expensive, behaves more like stock (higher delta). For directional bets, ATM or slightly OTM is a common balance.
- **Selling premium:** When **selling** options (e.g. covered call, put, spread), prefer **OTM** strikes to reduce assignment risk and to profit from theta. Don’t sell **too far** OTM or premium may not justify the risk.
- **Earnings and events:** IV often **spikes** before earnings. Selling premium (e.g. iron condor, strangle) can capture that, but **assignment** or a big move can hurt. Define max loss; consider defined-risk strategies only.

---

## 3. Strategy Selection Tips

- **Directional:** Long call (bullish) or long put (bearish) = simple, limited risk. For **cheaper** exposure, use **spreads** (bull call, bear put) and accept capped upside.
- **Neutral / income:** **Covered call** on stock you own; **cash-secured put** if you’re willing to buy stock at strike. **Iron condor** or **credit spread** when you expect range. Always define **max loss** before entering.
- **Volatility:** **Long straddle/strangle** when you expect a **big move** but are unsure of direction (e.g. earnings). Buy when IV is **low** (cheap). **Short** straddle/strangle when you expect **low** volatility—high risk; use only with defined risk (e.g. iron condor).
- **Hedging:** **Protective put** on stock = insurance. **Collar** (covered call + put) = cap upside and downside. Choose strike and expiration to match the **risk** you want to hedge and the **cost** you’re willing to pay.

---

## 4. Implied Volatility (IV) Tips

- **IV rank / IV percentile:** Compare current IV to **past** IV (e.g. last 52 weeks). High IV rank = options are **expensive** (good to sell premium, bad to buy). Low IV rank = options **cheap** (good to buy, less attractive to sell).
- **IV crush:** After **earnings** or an event, IV often **drops** (IV crush). Long options can lose even if the stock moves in your direction. If you’re long options into an event, you need a **large** move to overcome crush. Consider selling premium instead, or closing before the event.
- **Skew:** Puts often trade **richer** than calls (higher IV for OTM puts). Reflects demand for protection. When selling, OTM puts can yield more premium; when buying, consider put spreads to reduce cost.

---

## 5. Risk and Position Management

- **Max loss first:** Before every trade, know **max loss** (e.g. spread width − credit, or premium paid). **Size** so that max loss is acceptable (e.g. 1–2% of account per trade).
- **No naked short options** (or only tiny size): Naked short call = unlimited loss; naked short put = large loss to zero. Use **spreads** or **covered** structures to define risk.
- **Assignment:** Short **call** → assigned = sell stock (need to deliver shares). Short **put** → assigned = buy stock at strike. If you don’t want assignment, **close or roll** before expiration. Know your broker’s assignment rules and deadlines.
- **Early exercise (American):** Deep ITM American options can be exercised early. If you’re short, you can be assigned. Monitor as expiration approaches; close or roll if you don’t want stock.
- **Diversification:** Don’t concentrate in **one** name or **one** expiration. Spread risk across underlyings and dates.

---

## 6. Combining With TA and FA

- **FA for underlying:** Use fundamentals to **choose** the stock (quality, value). Don’t trade options on names you wouldn’t own as stock (unless it’s a defined, short-term trade).
- **TA for timing:** Use **technical** entry (e.g. support, breakout) to open options. Align **expiration** with expected time to target (e.g. next resistance in 2 months → 2–3 month option). Use TA for **stop** (e.g. close option if stock breaks support).
- **Options for structure:** Use options to **limit** risk (spreads), **hedge** (protective put), or **reduce** cost (spread instead of long call). Don’t use options to **over-leverage** a weak thesis.

---

## 7. Common Pitfalls and Quick Fixes

| Pitfall | Quick fix |
|---------|-----------|
| Buying short-dated options “for a quick move” | Use at least 30–45 DTE (or more) so theta doesn’t wipe you before the move. |
| Selling naked options | Use spreads or covered structures; define max loss. |
| Ignoring IV | Check IV rank; avoid buying when IV is very high; consider selling when IV is high. |
| Holding short options through expiration | Close or roll before expiration unless you want assignment. |
| Sizing too large | Size by max loss (e.g. 1% of account per trade). |
| No plan for assignment | Decide in advance: want stock or not? Close or roll if not. |
| Chasing momentum with options | Use TA/FA for entry; don’t buy OTM calls just because stock is up 10%. |

---

## 8. Pre-Trade Checklist (Options)

- [ ] I know my **view** (direction, range, or volatility).
- [ ] I chose a **strategy** that matches the view and my risk tolerance.
- [ ] I know **max loss** and have **sized** position accordingly.
- [ ] I checked **IV** (high vs low) and whether I’m buying or selling premium.
- [ ] **Expiration** matches my time horizon (not too short for long options).
- [ ] I have a plan for **assignment** (if short) or **exit** (take profit / stop).
- [ ] I’m not over-concentrated in one name or expiration.

---

*See also: [Options Trading Summary](../Summary/Options_Trading_Summary.md) | [Book Notes](../stock-market-analysis/options-trading/book-notes/README.md).*
