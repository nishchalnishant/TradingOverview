# Quant Trading and Strategy Automation

## Concept

**Quantitative (algo) trading** uses **programmed rules** to:
- **Generate signals** (e.g. when price crosses MA, or RSI < 30 at support).
- **Size positions** (e.g. 1% risk per trade from ATR and account size).
- **Execute orders** (e.g. send limit order at level, or market order on signal).
- **Manage risk** (e.g. max positions, max daily loss, stop orders).

**Automation** means the **computer** runs the strategy (often 24/5 or 24/7 for crypto) so that **emotion** and **delay** are reduced. It does **not** mean the strategy is good—garbage in, garbage out. The edge still comes from **logic** and **risk management**.

---

## Why Automate?

- **Discipline:** No skipping stops or moving targets; the code does what you defined.
- **Speed:** React to signals in milliseconds if needed (e.g. for scalping or market making).
- **Scale:** Run the same strategy on **many** symbols or timeframes without watching each chart.
- **Backtest:** Code is **testable**; you can backtest and walk-forward before going live.

---

## Levels of Automation

1. **Manual with checklist:** You trade by hand but use a **written** checklist (rules) and optionally a **script** that prints “BUY” or “SELL” (signal only).
2. **Semi-automated:** Strategy generates **alerts** or **signals**; you **place orders** yourself. Good first step.
3. **Fully automated:** Strategy sends **orders** to the broker via API. You monitor and intervene only for exceptions (e.g. disconnect, bad fill).

Start with **1 or 2**; move to **3** only when the strategy is validated and you understand execution (slippage, partial fills, errors).

---

## Strategy Automation Workflow

1. **Define rules** (entry, exit, stop, size) in plain language.
2. **Code** the rules (e.g. Python, Pine Script).
3. **Backtest** on historical data; check metrics and robustness.
4. **Paper trade** (or small size) in real time.
5. **Go live** with limits (size, max loss, symbols).
6. **Monitor** (logs, P&L, drawdown); **update** only with a process (no ad-hoc code changes in panic).

---

## Trading Psychology

- **Trust the system:** If you override the algo often (“I know better”), you’re not really algo trading—you’re discretionary with a crutch. Either **follow** the algo or turn it off and trade manually.
- **Avoid over-optimization:** Automating a **curve-fitted** strategy just loses money faster. Keep rules **simple** and **robust**.

---

*See also: [APIs and Data](apis-and-data.md) | [10 — Backtesting](../10-backtesting/README.md)*
