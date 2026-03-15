# Risk:Reward Ratio and Kelly Criterion

## Risk:Reward Ratio (R:R)

- **Definition:** Ratio of **potential profit** (target − entry) to **potential loss** (entry − stop). R:R = 2 means you risk 1 unit to make 2.
- **Why it matters:** With a **positive edge** (win rate × avg win > loss rate × avg loss), higher R:R can mean fewer wins needed for profitability. Example: 40% win rate and 1:2 R:R → (0.4 × 2) − (0.6 × 1) = 0.2 R per trade on average.
- **Minimum R:R:** Many traders aim for **at least 1:1.5** or **1:2** so that a 50% win rate still yields positive expectancy. In practice, **target** and **stop** should be set by **structure** (e.g. next resistance, below HL), then check if R:R is acceptable; if not, skip the trade or adjust.

---

## Expectancy

- **Expectancy (per trade)** = (Win rate × Avg win) − (Loss rate × Avg loss). In “R” terms: E = (Win rate × R) − (Loss rate × 1) if you risk 1R per trade and target R. Example: 50% win rate, 1:2 R:R → E = (0.5 × 2) − (0.5 × 1) = 0.5 R per trade.
- **Use:** Only trade setups that have **positive expectancy** over a large sample (backtest or tracked live).

---

## Kelly Criterion (Optional)

- **Concept:** Formula for **optimal bet size** (as fraction of bankroll) to maximize long-term growth, given win rate and win/loss ratio.
- **Formula (simplified):** f* = (p × b − q) / b, where:
  - f* = fraction of bankroll to risk per trade
  - p = win rate, q = 1 − p
  - b = win/loss ratio (avg win / avg loss in same units)
- **Example:** Win rate 50%, b = 2 (1:2 R:R). f* = (0.5 × 2 − 0.5) / 2 = 0.25. So “full Kelly” would risk **25%** per trade—**far too aggressive** for most traders.
- **In practice:** Use **fractional Kelly** (e.g. ¼ or ½ Kelly) to reduce volatility and drawdown. Or ignore Kelly and stick to a **fixed** 0.5–2% risk per trade, which is conservative and robust.

---

## Trading Psychology

- **Over-optimizing R:R:** Seeking only 1:5 trades can mean very few trades and missed opportunity. Balance **frequency** and **quality** (positive expectancy with acceptable R:R).
- **Moving targets:** Letting winners run (trailing) improves effective R:R but can reduce win rate. Track **average R** on winners in your journal.

---

## Risk Management

- **Position size** is still driven by **stop distance** and **risk%** (see [Position Sizing](position-sizing-and-risk-per-trade.md)). R:R and Kelly inform **whether** to take the trade and **how much** you might theoretically risk—but in practice, cap risk per trade (e.g. 1–2%) for psychological and drawdown control.

---

*See also: [Position Sizing](position-sizing-and-risk-per-trade.md) | [Drawdown and Portfolio Risk](drawdown-and-portfolio-risk.md)*
