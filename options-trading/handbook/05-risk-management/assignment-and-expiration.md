# Assignment and Expiration

## Assignment Mechanics

Assignment occurs when the **holder of a long option exercises their right**, causing the short option writer to fulfill the corresponding obligation.

| Short Position | Assignment Means |
|---------------|-----------------|
| Short call | Must sell 100 shares at the strike price |
| Short put | Must buy 100 shares at the strike price |

Assignment is handled automatically by the Options Clearing Corporation (OCC). If your short option is ITM and assigned, your brokerage will debit or credit shares and cash accordingly overnight.

**Key fact:** You cannot control when you are assigned on an American-style option. Assignment can occur any time the short option is in the money, but in practice it is most common at expiration or in specific circumstances (dividends, early exercise).

---

## Early Assignment Risk

Early assignment on American-style options is possible but uncommon for most situations. It becomes likely when:

### Short Calls: Dividend Ex-Date Risk

When a stock pays a dividend, the call holder may exercise early to capture the dividend.

- **When:** Typically the day before the ex-dividend date
- **Why:** If the dividend amount exceeds the remaining time value in the call, it is rational to exercise and collect the dividend rather than hold the call
- **Who is at risk:** Short ITM call holders, especially on deep ITM calls close to dividend ex-date
- **Prevention:** Close or roll short calls that are deep ITM before the ex-dividend date when dividends are large

### Short Puts: Deep ITM with No Time Value

When a short put is deep in the money with little remaining time value, the put holder may exercise early to receive cash immediately.

- **When:** Usually in low-interest-rate environments with very deep ITM puts
- **Why:** The put holder gives up almost nothing in time value but receives the strike price immediately, which can be invested
- **Who is at risk:** Short put sellers whose position has moved dramatically against them
- **Prevention:** Close or roll short puts that are significantly ITM to avoid surprise assignment

### What to Do After Unexpected Early Assignment

1. Check your account before market open — assignment notifications come overnight
2. If assigned on short call: your shares have been sold. Decide whether to rebuy or leave the position closed.
3. If assigned on short put: you now own shares at the strike price. Your effective cost basis = strike − premium received. Decide whether to hold and sell covered calls, or sell the shares.
4. If you don't have shares to deliver on a short call assignment (naked call): your broker will short the stock on your behalf. Close immediately if this is not your intent.

---

## Managing Expiration Week

The final week before expiration is the highest-risk period for short options:
- **Gamma is at its maximum** — small moves create large delta changes
- **Theta still decays but the remaining value is small** — not worth holding for the last few cents
- **Pin risk:** A stock that closes exactly at or just above/below your short strike at expiry creates uncertainty about whether you will be assigned

### When to Close Early

| Situation | Action |
|-----------|--------|
| Position has reached 50% of max profit | Close regardless of DTE — take the win |
| Expiration is 21 DTE away | Evaluate: if not at 50% profit, consider closing at a smaller gain to eliminate gamma risk |
| Stock is testing or has breached short strike | Close the threatened side; hold the untested side |
| Event risk (earnings, FOMC) in the expiration period | Close before the event to avoid IV spike or large gap |
| Final 5 DTE, still have full short position | Close all short options unless you want assignment/exercise |

### When to Hold to Expiry

- Long options that have not reached your profit target and you want to see if the move continues
- Long spreads where both legs expire deep ITM/OTM and closing costs more in commissions than the remaining value
- Credit spreads where your short leg is far enough OTM that assignment is not a concern and you want the last few cents of decay

**Important:** Don't let small-premium short options expire ITM by accident. A $0.05 short option that you forgot to close can be assigned, creating a full 100-share stock position overnight.

---

## Rolling: Extending and Adjusting Positions

Rolling means simultaneously closing an existing option position and opening a new one at a different expiration, different strike, or both.

### Types of Rolls

| Roll Type | Action | Purpose |
|-----------|--------|---------|
| **Roll out** | Close current expiry, open same strike at farther expiry | Extend time; give position more time to work |
| **Roll up** (calls) | Close current strike, open higher strike | Reduce delta risk on short call; collect additional credit |
| **Roll down** (puts) | Close current strike, open lower strike | Reduce delta risk on short put |
| **Roll up and out** | Both change strike and extend expiry | Most common defensive roll: manage a challenged position |
| **Roll for credit** | Execute any roll while collecting a net credit | Never pay a debit to roll a short options position |

### The "Roll for Credit" Rule

**Always roll short options positions for a net credit.** If you cannot receive a credit by rolling (because the position has moved too far against you), it is better to take the loss and close the trade than to roll for a debit:

- Rolling for a debit increases your total risk without adding meaningful probability of recovery
- Rolling for a credit at least adds to your breakeven and gives you more time without increasing max loss

**Exception:** Defensive roll on long-term position (covered call on a stock you want to keep) where paying a small debit to avoid assignment makes sense economically (cost basis change, tax considerations).

### Practical Roll Example

Short 95 Put credit spread (95P/90P) collected $1.50 credit. Stock has fallen to $96, 21 DTE. Short 95P is at $2.50 (losing $1.00).

Options:
1. **Close for a loss** → Buy back at $2.50, realize −$1.00 loss (vs $1.50 max gain → total outcome −$1.00 on the spread)
2. **Roll out:** Buy current 95P/90P spread, sell next month 93P/88P for $1.80 credit
   - Net: paid $1.00 to close, received $1.80 on new spread → net credit of $0.80
   - New max loss: $5.00 − ($1.50 + $0.80) = $2.70 (vs $3.50 original)
   - New breakeven: $90.70 (better than original $93.50)
3. **Do nothing and hope** → highest gamma risk; avoid unless you have very high conviction on a recovery

---

## Practical Management Rules (Industry Standards)

These rules are derived from systematic options selling research (TastyTrade, Optionality, CBOE studies):

| Rule | Detail |
|------|--------|
| **50% profit target** | Close short premium positions when the credit received has fallen to 50% of original. A $2.00 credit → buy back at $1.00. Mathematically optimal for risk-adjusted returns. |
| **21 DTE management** | At 21 days to expiration, evaluate all short positions. Close those not at profit targets; roll those you want to extend. |
| **2× loss limit** | If a short position has grown to 2× the original credit received, close. Don't hold a $2.00 credit and let it turn into a $6.00 loss. |
| **No earnings holding** | Close short options positions before an earnings announcement unless you have explicit event strategy (defined risk iron condor, etc.). |
| **Never average into losers** | Adding more short options to a losing position increases risk, not decreases it. Adjust position size or close, never add naked exposure. |

---

## Assignment on Spreads

For credit spreads, assignment risk affects the short leg only. The long leg provides protection.

**Scenario:** Short 95P/Long 90P bull put spread. Stock crashes to $88 at expiry.
- Short 95P assigned: you buy 100 shares at $95 (cost $9,500)
- Long 90P exercised: you sell 100 shares at $90 (receive $9,000)
- Net loss: $500 per spread = $5 spread width × 100 = $500, minus credit received

This confirms the maximum loss calculation. The spread structure fully contains the loss even when both legs are deep ITM.

**Practical note:** Brokers may not automatically exercise your long leg if they receive an assignment notice on the short leg. Always check and exercise manually if needed to limit loss. Some brokers auto-exercise ITM long options, but confirm with your broker's policy.

---

## Summary: Expiration and Assignment Rules

| Rule | Action |
|------|--------|
| Close short options at 50% profit | Don't wait for max gain — the risk isn't worth the remaining reward |
| Evaluate all positions at 21 DTE | Close, roll, or confirm hold with clear reasoning |
| Watch dividend ex-dates on short ITM calls | Close before ex-date if time value < dividend amount |
| Roll for credit only | If you can't roll for credit, close and accept the loss |
| Know your broker's exercise policy | Confirm long legs are exercised on assignment |
| Never forget a small short option near expiry | $0.05 ITM can still be assigned; close all short positions intentionally |
