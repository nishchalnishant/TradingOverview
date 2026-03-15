# Section 11 — Algorithmic Trading (Basic)

Algorithmic (quant) trading uses **rules and code** to generate signals and often to **execute** trades automatically. This section is an **intro**: strategy automation, APIs, backtesting frameworks, data sources, and a simple Python stack.

---

## Contents

| Document | Topic |
|----------|--------|
| [Quant Trading and Automation](quant-trading-and-automation.md) | What algo trading is; strategy automation |
| [APIs and Data](apis-and-data.md) | Broker/data APIs; data sources |
| [Backtesting Frameworks and Stack](backtesting-frameworks-and-stack.md) | Python stack; backtesting libraries |

---

## Key Ideas

- **Algo trading:** Define rules in code → backtest → run live (manually or automated). Reduces **discretion** and **emotional** execution.
- **APIs:** Brokers and data providers offer **APIs** to fetch data, get quotes, and place orders. Used for **automation** and **research**.
- **Stack:** Python + pandas + backtesting library (e.g. backtrader, vectorbt) + data source + (for live) broker API. Start with **backtest**; add **live** only when strategy and execution are clear.

---

## Quick Links

- Backtesting: [10 — Backtesting](../10-backtesting/README.md) | Risk: [08 — Risk Management](../08-risk-management/README.md)
