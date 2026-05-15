# Scalping Strategies

## Concept

**Scalping** is short-term trading with **small profit targets** and **quick exits**—often holding for seconds to minutes. The edge comes from **many** small wins and tight risk control. It requires focus, fast execution, and low costs (spread, commissions).

---

## Setup Conditions

- **Timeframe:** Usually **1m, 5m** or tick charts. Higher timeframe (e.g. 15m) for **bias** (e.g. only scalp long when 15m is bullish).
- **Liquidity:** Trade **liquid** instruments (tight spread, enough volume) so that entry/exit don’t move price and costs are minimal.
- **Session:** Scalping is often done in **high-volume** sessions (e.g. London, NY open) when spread is tight and moves are clean.
- **Levels:** Use **key levels** (VWAP, prior high/low, round number) or **order flow** (tape, delta) for quick entries.

---

## Entry Criteria

- **Level-based:** Price at support (long) or resistance (short); quick bounce or rejection. Enter on first candle that confirms (e.g. bullish candle at VWAP).
- **Momentum:** Short-term momentum (e.g. break of 1m high with volume). Enter on the break or first pullback.
- **Order flow (if available):** Aggressive buying (delta, tape) at a level; go long with the flow. Keep trades **short**—in and out.
- **Confirmation:** One or two candles; no need for multiple confirmations (speed matters).

---

## Exit Criteria

- **Target:** **Small**—e.g. 3–10 ticks, or 0.05–0.1% in equities, or 1:0.5 to 1:1 R:R. Scalpers often take profit quickly.
- **Stop:** **Tight**—e.g. 3–10 ticks or just beyond the level. One or two candles against you = exit.
- **Time:** If the trade doesn’t work in 1–5 minutes, many scalpers exit (no hanging in hope).
- **Trailing:** Rare for classic scalping; usually fixed target and stop.

---

## Stop Loss Placement

- **Very tight:** Below the entry candle low (long) or above the entry candle high (short). Or just beyond the level (support/resistance). Goal: small loss per trade so you can take many trades.
- **Risk per trade:** Even with small $ risk per trade, **number of trades** can add up. Ensure daily risk is capped (e.g. max 5–10 scalps per day, or max daily loss).

---

## Risk:Reward Analysis

- **R:R:** Often **1:0.5 to 1:1** (risk 1 to make 0.5–1). Win rate must be **high** (e.g. 60%+) for positive expectancy. Or: **1:1** with 55% win rate = edge.
- **Costs:** Spread and commission matter a lot. If round-trip cost is 2 ticks and your target is 4 ticks, you need a high win rate. Prefer **low-cost** instruments and **limit orders** where possible.

---

## Backtesting Suggestions

- **Include costs:** Model **spread and commission** on every trade. Scalping is sensitive to costs.
- **Slippage:** Assume 1–2 ticks slippage on market orders in backtest to avoid overstating results.
- **Data:** Tick or 1m data for realistic entry/exit. Test on multiple days and instruments.
- **Metrics:** Win rate, average R, profit factor, number of trades per day. Ensure strategy is **tradeable** (not too many signals, execution feasible).

---

*See also: [01 — Bid, Ask, Spread](../01-market-basics/bid-ask-spread.md) | [08 — Risk Management](../08-risk-management/README.md)*
