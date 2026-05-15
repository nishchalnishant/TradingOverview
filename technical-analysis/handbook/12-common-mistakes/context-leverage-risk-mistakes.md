# Ignoring Context, Overleveraging, and Lack of Risk Management

## Ignoring Market Context

**Problem:** Taking the same signal in every condition — e.g. buying every RSI < 30 without checking if the market is trending down (where RSI can stay low for weeks) or at support (where an oversold RSI can mean a genuine bounce opportunity).

### Specific Context Mistakes

#### Trading Against the Trend

| Mistake | Example | Consequence | Fix |
|---|---|---|---|
| Buying oversold in a downtrend | RSI < 30 in a falling market, no structure support | Price continues lower; stopped out repeatedly | Only take long signals when higher-timeframe trend is up |
| Shorting in an uptrend | Sell at resistance in a strong bull run | Price breaks resistance and runs further | Wait for trend shift confirmation (CHoCH, lower high) before fading |
| Ignoring higher-timeframe bias | Taking short on 5-min without checking daily structure | Daily trend absorbs the short signal | Always check at least one TF above your entry TF |

A signal aligned with the trend has a higher base rate of success simply because price is already moving in that direction. A counter-trend signal requires a much more precise setup (strong reversal structure, high-volume exhaustion candle, major level) to be worth taking.

#### Ignoring Session and Time of Day

| Mistake | Example | Consequence | Fix |
|---|---|---|---|
| Trading breakouts in pre-market | Buy breakout at 8:15 AM EST on thin volume | False breakout reverses at market open | Wait for confirmed volume at open; treat pre-market moves with skepticism |
| Holding into low-liquidity hours | Swing trade into weekend on crypto | Wide spreads, sudden gap through stop | Close or reduce before low-liquidity periods; widen stops explicitly if holding |
| Expecting Asian range breakouts to follow through into NY | Buy London breakout expecting NY to extend | NY session reverses and hunts the Asian range | Know which session drives which instrument (e.g. NY for US equities, London for EUR/USD) |

#### Ignoring News and Events

| Mistake | Example | Consequence | Fix |
|---|---|---|---|
| Holding a position through earnings | Long stock into Q3 earnings expecting beat | Miss beats can still sell the news; beat can gap lower | Check earnings calendar; decide before open whether to hold or close |
| Entering just before CPI or FOMC | Buy breakout 10 minutes before CPI print | Print causes reversal; stop hit by spike | Check the macro calendar daily; avoid new entries within 30–60 min of major events |
| Adding to a position before known binary events | Scale into a long ahead of FDA decision | Binary outcome; gap can exceed stop distance | Binary events warrant reduced or flat size; optionality is better expressed with options |

---

## Overleveraging

**Problem:** Using high leverage (e.g. 50:1 in forex, 10x in crypto) so that a small adverse move wipes the account or triggers a margin call. One or two bad trades can mean total loss of capital.

### Specific Leverage Mistakes

#### Over-Sizing Positions

| Mistake | Example | Consequence | Fix |
|---|---|---|---|
| Risking 10%+ per trade | $10,000 account, $1,000 at risk on a single trade | Three consecutive losses = 30% drawdown; hard to recover | Cap risk at 1–2% per trade maximum; 0.5% when learning |
| Using maximum broker leverage | 50:1 on forex; 1% move = 50% account move | Margin call on a routine market swing | Treat leverage as a tool for capital efficiency, not for amplifying size beyond risk budget |
| Not accounting for correlated positions | Long AAPL, MSFT, QQQ simultaneously | All drop together on risk-off day; total loss = 3x a single trade | Treat correlated positions as one combined exposure; reduce each accordingly |

#### Adding to Losing Positions (Averaging Down)

This is one of the most dangerous habits in trading. Adding to a loser assumes the original thesis is correct and the market is wrong — but the market is the arbiter of price.

| Mistake | Example | Consequence | Fix |
|---|---|---|---|
| Doubling down on a losing trade | Buy at $100, price drops to $90, buy more | Position size doubles as trade moves further against you | If a trade needs averaging down to "make back" losses, the setup was wrong; exit the original, not add |
| Averaging down in a trending market | Adding to a short in a strong uptrend | Trend continuation accelerates losses on the larger position | Averaging down works occasionally in range-bound markets but is lethal in trends |
| No cap on average-down process | Adding 3, 4, 5 times | Eventually one large position with a cost basis far from market price | If you must scale in, the full position size must be defined **before** the first entry; total risk must be fixed |

**Rule:** The only acceptable time to add to a position is when the trade is going **in your favor** (scaling in on confirmation) and total risk on the full position remains within your defined limit.

---

## Lack of Risk Management

### No Fixed Risk Per Trade

Trading with inconsistent size ("this one feels good, so I'll put more in") means one large loss can wipe out many small wins. The math of expectancy only works if position size is consistent.

- Fix: Position size = (Account × Risk%) / (Entry − Stop). This is not optional.

### No Maximum Daily Loss

Trading through a bad day and doubling down on losses to "get it back" is one of the fastest ways to blow an account. Losses compound; psychology degrades; decisions get worse.

| Scenario | Without Daily Loss Limit | With 2% Daily Loss Limit |
|---|---|---|
| 5 consecutive bad trades at 1% risk each | 5% drawdown; emotional spiral likely | Trading halted at −2%; max damage contained |
| One catastrophic loss of 5% on an oversized trade | Major drawdown; may take weeks to recover | Oversized trade not possible under rules |

- Fix: Set a hard daily loss limit (e.g. 2% of account). When hit, close all positions, stop trading for the day. No exceptions.

### Moving Stops Against the Trade

Moving a stop further away when price approaches it is not risk management — it is hope masquerading as a plan. Every time you move a stop, you are implicitly choosing to take a larger loss.

| Mistake | Example | Consequence | Fix |
|---|---|---|---|
| Moving stop further on a losing trade | Stop at $95, price drops to $96, move stop to $92 | Loss grows from 5% to 8%; stop may be moved again | Define the stop **before** entry; treat a stop as the point where the setup is invalid, not just uncomfortable |
| Widening stop after news spike | Stop triggered by CPI spike; you move it to give more room | Stop was correct; the trade invalidated by new information | If an event changes the thesis, that is an exit signal, not a reason to widen |

Stops should only ever move **in the direction of the trade** (to lock profit or to breakeven) — never against it.

### Revenge Trading

Revenge trading occurs when a loss triggers an emotional need to "win it back" immediately. This leads to:
- Taking low-quality setups out of frustration.
- Increasing position size to recover faster.
- Breaking all pre-defined rules.

| Stage | What Happens |
|---|---|
| Loss #1 | Normal; accept and move on |
| Revenge trade (Loss #2) | Setup was poor; taken out of emotion; loss is larger |
| Escalation (Loss #3+) | Sizing increases; rules abandoned; cascade of losses |

- Fix: Implement a mandatory cool-down after any loss that feels emotional. A rule like "if I close a position at a loss and feel the urge to enter immediately, I must wait 15 minutes and review the setup checklist" prevents most revenge trades.

### Not Using Stops

Trading without stops is the same as having no risk management. The implicit assumption is that you will exit manually if the trade goes against you — but in practice, ego and loss aversion cause most traders to hold losing positions too long.

- Fix: Every trade must have a defined stop before entry. The stop does not need to be a hard stop order (it can be mental) but it must be written down and adhered to without exception.

---

## Chasing Trades

**Problem:** Entering after a big move because of FOMO (e.g. buying the top of a pump, or entering a breakout that is already 3 ATRs extended). Usually results in a poor entry and quick stop out.

| Scenario | What Chasing Looks Like | What to Do Instead |
|---|---|---|
| Missed a breakout | Buy 2% above the breakout level with original stop still at the base | Wait for a pullback to the breakout level; if no pullback, accept the miss |
| FOMO on a parabolic move | Buy a stock up 40% on news with no defined stop | Parabolic moves can reverse violently; if not in before the move, it is usually too late |
| Entering after a strong candle | Market order into a wide-range candle at its close | You are buying the high of the candle; risk/reward is now negative | Wait for the next pullback or next setup |

---

## Comprehensive Mistake Summary

| Mistake | Consequence | Fix |
|---|---|---|
| Trading against higher-timeframe trend | Low base-rate setups; frequent stop-outs | Check 1–2 TFs above; align with trend direction |
| Ignoring session and liquidity | False breakouts; slippage; gaps through stops | Know your instrument's active session; avoid low-liquidity periods |
| Entering before major news events | Binary outcome; stop meaningless | Check calendar; flat or reduced before events |
| Over-leveraging | Single trade can cause catastrophic drawdown | 1–2% max risk per trade; leverage ≠ edge |
| Adding to losers | Loss grows; larger position in wrong direction | Average up (with position-size cap), never down |
| No daily loss limit | Emotional cascade; weeks of gains erased in a day | Hard stop at −2% per day; walk away when hit |
| Moving stops against the trade | Larger losses; hope replacing plan | Stops move only toward profit, never against |
| Revenge trading | Low-quality setups; escalating losses | Mandatory cooling-off period after emotional loss |
| No stops | Holding losing trades indefinitely; margin call | Every trade has a predefined stop before entry |
| Chasing | Poor entry; negative risk/reward at entry | Wait for pullback or skip the trade |

---

*See also: [08 — Risk Management](../08-risk-management/README.md) | [09 — Trading Psychology](../09-trading-psychology/README.md) | [Beginner Mistakes](beginner-mistakes-indicator-overload.md)*
