# Quant Trading and Strategy Automation

## Concept

**Quantitative (algo) trading** uses **programmed rules** to:
- **Generate signals** (e.g. when price crosses MA, or RSI < 30 at support).
- **Size positions** (e.g. 1% risk per trade from ATR and account size).
- **Execute orders** (e.g. send limit order at level, or market order on signal).
- **Manage risk** (e.g. max positions, max daily loss, stop orders).

**Automation** means the **computer** runs the strategy (often 24/5 or 24/7 for crypto) so that **emotion** and **delay** are reduced. It does **not** mean the strategy is good — garbage in, garbage out. The edge still comes from **logic** and **risk management**.

---

## Types of Quantitative Strategies

### 1. Trend Following

Buy (or go long) instruments that have been going up; sell (short) instruments that have been going down. Captures extended directional moves.

- **Signals**: Moving average crossovers, Donchian channel breakouts, momentum scores (e.g. 12-month return).
- **Timeframe**: Works best on daily/weekly bars over weeks to months.
- **Characteristics**: Low win rate (30–45%), high average win-to-loss ratio. Long periods of drawdown in choppy markets.
- **Examples**: Turtle Trading system, dual moving average crossover, time-series momentum (TSMOM).

### 2. Mean Reversion

Bet that an extreme deviation from a historical average will revert back. Buy oversold conditions; sell overbought.

- **Signals**: RSI extremes at support/resistance, Bollinger Band touches, z-score of spread between price and moving average.
- **Timeframe**: Intraday to swing (hours to days).
- **Characteristics**: High win rate (55–70%), smaller average win. Vulnerable to trending markets where "oversold" keeps getting more oversold.
- **Examples**: RSI(2) strategy, pairs trading with z-score entry, overnight gap fill.

### 3. Statistical Arbitrage (Stat Arb)

Exploit temporary mispricings between related instruments. The spread between two correlated assets (e.g. two ETFs tracking the same index) reverts to zero.

- **Signals**: Cointegration tests (Engle-Granger, Johansen), z-score of spread between two instruments.
- **Timeframe**: Intraday to multi-day.
- **Characteristics**: Requires two legs (long one, short the other) simultaneously. Requires careful beta-hedging. Works until it breaks (pairs can decouple permanently).
- **Examples**: ETF vs underlying basket, ADR vs domestic share, sector ETF pairs.

### 4. Market Making

Continuously post a bid below and an ask above the current mid-price. Capture the bid-ask spread as inventory turns over.

- **Signals**: Order book imbalance, volatility estimates for spread width.
- **Timeframe**: Milliseconds to seconds (HFT domain for pure market making; retail adaptations exist).
- **Characteristics**: High win rate, tiny per-trade profit, large volume requirement. Huge risk during fast markets or sudden news.
- **For retail traders**: A scaled-down version is limit order scalping on illiquid instruments, or selling options premium (theta decay as synthetic spread).

### Strategy Comparison

| Strategy Type | Win Rate | Avg Win:Loss | Market Condition | Main Risk |
|---|---|---|---|---|
| Trend Following | 35–45% | 2:1 to 5:1 | Trending markets | Range-bound periods |
| Mean Reversion | 55–70% | 1:1 to 1.5:1 | Ranging markets | Strong trending moves |
| Stat Arb | 60–75% | 1:1 to 2:1 | Any (market-neutral) | Pair decoupling |
| Market Making | 70–85% | 0.5:1 to 1:1 | Liquid, stable markets | Fast directional moves |

---

## Workflow: Hypothesis to Live Trading

### Step 1 — Hypothesis
Start with an **economic or behavioral rationale**, not a pattern found by data mining. Examples:
- "Momentum persists because institutional investors accumulate over weeks" (trend following).
- "Retail overreaction to short-term news creates extreme RSI readings that snap back" (mean reversion).

### Step 2 — Define Rules Precisely
Write rules in plain language before coding. Every ambiguous word will become a bug:
- Entry trigger (exact condition, which bar, market vs limit)
- Stop placement (fixed ATR multiple, structural level, percent)
- Profit target or trailing exit
- Position size formula
- Max positions and max daily loss kill-switch

### Step 3 — Backtest
Code the rules exactly as written. Validate that the code matches the rules by running on a short period and checking each trade manually.

Key backtest checks:
- Realistic commissions and slippage (at minimum 1–2 ticks per side).
- No look-ahead bias (see Pitfalls section below).
- Enough in-sample trades for statistical significance (minimum 200 trades; more for low win-rate strategies).

### Step 4 — Walk-Forward Validation
Run walk-forward testing across multiple IS/OOS windows. Require Walk-Forward Efficiency Ratio > 0.5. See [Walk-Forward and Forward Testing](../10-backtesting/walk-forward-forward-testing.md).

### Step 5 — Paper Trading
Run the strategy in real time without real capital. Track every signal, fill assumption, and P&L. Duration: at minimum 30–100 trades depending on strategy frequency.

What to verify in paper trading:
- Signals are generated at the correct time (not end-of-bar look-ahead).
- Order routing logic handles partial fills and rejected orders.
- API connections and data feeds are stable.

### Step 6 — Go Live at Minimum Size
Trade with the smallest position size your broker allows. The goal is to stress-test execution, not make money. Verify actual fills vs simulated fills.

### Step 7 — Scale and Monitor
Scale only after verifying that live results match paper trading metrics within an acceptable range. Set hard limits:
- Maximum position size per instrument
- Maximum daily loss (auto kill-switch)
- Maximum drawdown from equity peak before human review is required

---

## Common Pitfalls

### Look-Ahead Bias
Using data in the backtest that would not have been available at the time of the signal.

| Example | How It Happens | Fix |
|---|---|---|
| Using today's close to generate a signal, then executing at today's close | Signal and execution on the same bar | Execute on the **next bar's open** |
| Using adjusted close prices to detect "clean" levels | Adjustments are applied retroactively | Use unadjusted data for entry levels; use adjusted only for returns |
| Using future rebalancing data for index membership | Backtest includes stocks added later | Use point-in-time index constituent data |

### Survivorship Bias
Backtesting only on instruments that still exist today ignores all the ones that failed, went bankrupt, or were delisted. This overstates performance for stock-selection strategies.

- Fix: Use a dataset that includes delisted and failed companies (e.g. CRSP for US equities).
- Impact: Strategies selecting from the S&P 500 today are biased — companies that survived to be in the index today outperformed; those that were removed did not.

### Overfitting (Curve-Fitting)
A strategy with too many parameters can fit the noise in historical data perfectly and generalize poorly to new data.

- Signs: Near-perfect backtest equity curve; very specific parameter values (RSI = 17, ATR multiplier = 2.37); performance collapses slightly outside the exact backtested parameter range.
- Fix: Reduce the number of free parameters; test a range of parameters and require that a **neighborhood** of values all perform well (parameter robustness); use walk-forward testing; apply out-of-sample holdout from the start.

### Transaction Cost Underestimation
Many backtests assume zero or minimal costs. For high-frequency strategies, commissions and spread can consume the entire edge.

- Fix: Include realistic commissions (per-share or per-trade), bid-ask spread (at least half the average spread), and market impact for large sizes.

### Ignoring Execution Reality
Backtest assumes you always get filled at the signal price. Live trading involves:
- Slippage on market orders (especially in fast markets).
- Partial fills on limit orders.
- Occasional missed signals due to latency or API errors.

---

## Levels of Automation

1. **Manual with checklist:** You trade by hand but use a written checklist (rules) and optionally a script that prints "BUY" or "SELL" (signal only).
2. **Semi-automated:** Strategy generates alerts or signals; you place orders yourself. Good first step.
3. **Fully automated:** Strategy sends orders to the broker via API. You monitor and intervene only for exceptions (e.g. disconnect, bad fill).

Start with 1 or 2; move to 3 only when the strategy is validated and you understand execution (slippage, partial fills, errors).

---

## Infrastructure Considerations

### Latency
- For strategies with holding periods of minutes to hours, execution latency of a few hundred milliseconds is usually irrelevant.
- For intraday scalping or arbitrage, latency matters: co-location (server physically near the exchange) and direct market access (DMA) are required.
- Rule of thumb: if your edge exists in seconds, you need institutional-grade infrastructure. If your edge exists in days, a well-coded Python script on a VPS is sufficient.

### Reliability and Uptime
A strategy that misses signals due to crashes, disconnections, or data feed outages will underperform its backtest.
- Use a **VPS or cloud server** (not your laptop) for 24/5 or 24/7 operation.
- Implement **heartbeat checks**: if the strategy has not traded or logged activity in X minutes, send an alert.
- Handle **reconnection logic**: data feed disconnects, broker API timeouts, and authentication refresh tokens need automatic recovery.
- Test failure modes: what happens if the data feed drops mid-trade? What if an order is submitted but no fill confirmation arrives?

### Monitoring and Alerting
Never deploy a live automated strategy without monitoring. Minimum monitoring stack:
- **Trade log**: every order submitted, filled, or cancelled with timestamp and price.
- **P&L tracking**: live unrealized and realized P&L vs expected.
- **Kill-switch**: automatic position close and halt if daily loss exceeds a threshold.
- **Alerts**: email or messaging (Telegram, Slack) on trade, error, or anomalous drawdown.

### Code Discipline
- Version-control all strategy code (Git).
- Never make ad-hoc code changes in a live running strategy to "fix" a losing trade.
- Maintain separate environments: development, backtesting, paper trading, live. Promote code through stages with tests.

---

## Trading Psychology

- **Trust the system:** If you override the algo often ("I know better"), you're not really algo trading — you're discretionary with a crutch. Either follow the algo or turn it off and trade manually.
- **Avoid over-optimization:** Automating a curve-fitted strategy just loses money faster. Keep rules simple and robust.
- **Separate the person from the performance:** When an automated strategy loses, resist the urge to change it immediately. Log the losses, compare to backtest expectations, and make changes only through a formal review process, not in response to emotion.

---

*See also: [APIs and Data](apis-and-data.md) | [Backtesting Frameworks and Stack](backtesting-frameworks-and-stack.md) | [10 — Backtesting](../10-backtesting/README.md)*
