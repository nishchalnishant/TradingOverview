# Master Summary — All Three Disciplines

A single-document overview of **Technical Analysis**, **Fundamental Analysis**, and **Options Trading** as covered in this repository. Use this for big-picture revision and to see how each discipline fits into a complete market-analysis framework.

---

## 1. Technical Analysis — Summary

**What it is:** Analysis of **price and volume** (and derived indicators) to identify trends, levels, and timing. Assumes that price reflects all known information and that patterns repeat.

**Core concepts:**
- **Market structure:** Support/resistance, trendlines, HH/HL (uptrend), LH/LL (downtrend), break of structure (BOS), market structure shift (MSS).
- **Candlestick patterns:** Single (Doji, Hammer, Shooting Star, Marubozu), two-candle (Engulfing, Piercing, Dark Cloud, Tweezer), three-candle (Morning/Evening Star, Three Soldiers/Crows, Inside/Outside bar).
- **Chart patterns:** Reversal (Head & Shoulders, double/triple top/bottom, rounded); continuation (flags, pennants, triangles, rectangle, cup and handle). Breakout confirmation and volume.
- **Indicators:** Trend (MA, EMA, VWAP, Ichimoku, Parabolic SAR); momentum (RSI, MACD, Stochastic, CCI); volatility (Bollinger, ATR, Keltner); volume (volume profile, OBV, A/D).
- **Advanced:** Order blocks, liquidity zones, Fair Value Gaps (FVG), Wyckoff (accumulation/distribution, springs, upthrusts).
- **Strategies:** Trend following, breakout, mean reversion, scalping, swing, position trading—each with entry/exit, stop, R:R.
- **Risk & psychology:** Position sizing (1% risk, size = $ risk / |entry − stop|), R:R ≥ 1:2, drawdown management, discipline, journaling, trading plan, biases.

**When to use:** Timing entries/exits, setting stops and targets, reading short- to medium-term price behavior. Works across timeframes (intraday to position).

**Full content:** [Technical Analysis Handbook](../stock-market-analysis/technical-analysis/handbook/README.md) | [Revision (cheat sheets)](../Revision/Complete_Trading_Revision.md)

---

## 2. Fundamental Analysis — Summary

**What it is:** Analysis of **financial statements**, **business quality**, and **valuation** to estimate intrinsic value and assess whether a security is under- or overvalued.

**Core concepts:**
- **Financial statements:** Income statement (revenue, expenses, profit); balance sheet (assets, liabilities, equity); cash flow statement (operating, investing, financing). Quality of earnings and red flags.
- **Key ratios:** Profitability (ROE, ROA, margins); liquidity (current, quick); leverage (debt/equity); valuation (P/E, P/B, P/S, EV/EBITDA); growth (revenue, earnings growth).
- **Valuation:** DCF (discounted cash flow), comparable multiples (P/E, EV/EBITDA), margin of safety. Fair value vs market price.
- **Qualitative:** Management, competitive advantage (moat), industry position, growth potential, ESG and risk factors.
- **Value vs growth:** Value = buy below intrinsic value (Graham, Buffett). Growth = focus on future earnings potential (Fisher, Lynch).

**When to use:** Stock selection, long-term holding conviction, avoiding overvalued or low-quality names. Complements technicals for *what* to trade.

**Full content:** [Fundamental Analysis](../stock-market-analysis/fundamental-analysis/README.md) | [Book Notes](../stock-market-analysis/fundamental-analysis/book-notes/README.md)

---

## 3. Options Trading — Summary

**What it is:** Trading **derivatives** (calls and puts) that give the right (not obligation for long options) to buy or sell an underlying at a set strike by expiration. Used for leverage, hedging, and structured payoffs.

**Core concepts:**
- **Definitions:** Call = right to buy; Put = right to sell. Strike, expiration, premium. In-the-money (ITM), at-the-money (ATM), out-of-the-money (OTM). American vs European style.
- **Greeks:** Delta (sensitivity to underlying); Gamma (rate of change of delta); Theta (time decay); Vega (sensitivity to volatility). Used for risk and position management.
- **Strategies:** Long call/put (directional); covered call (income); protective put (hedge); spreads (bull/bear call/put); straddle/strangle (volatility); iron condor (range). Each has defined risk/reward and use case.
- **Pricing:** Option value = intrinsic + time value. Volatility (implied vs historical) is central. Black-Scholes and binomial models (conceptual).
- **Risk:** Limited (long options) vs unlimited (short naked options). Margin, assignment, early exercise. Position sizing and diversification.

**When to use:** Leveraging a view (calls/puts), hedging equity (protective puts, collars), earning premium (covered calls, selling spreads), or expressing volatility views (straddles, strangles). Combines with TA (timing) and FA (underlying selection).

**Full content:** [Options Trading](../stock-market-analysis/options-trading/README.md) | [Book Notes](../stock-market-analysis/options-trading/book-notes/README.md)

---

## 4. How to Use All Three Together

| Step | Discipline | Role |
|------|------------|------|
| **Choose the asset** | Fundamental Analysis | Screen by quality, valuation, growth; avoid overvalued or weak fundamentals. |
| **Time the trade** | Technical Analysis | Enter on structure (support, breakout), set stop and target from price action. |
| **Structure the exposure** | Options (if used) | Use calls/puts/spreads to express view or hedge; manage size and cost with Greeks. |
| **Manage risk** | All three | FA = position size by conviction; TA = stops/targets; Options = defined risk, hedging. |

**Example (long equity idea):** FA says stock is undervalued and high quality → TA says wait for pullback to support and bullish candle → Enter stock or buy call; stop below support; target at next resistance or based on valuation.

---

## 5. Repository Map (Where to Find What)

| Topic | Location |
|-------|----------|
| **Technical Analysis (full handbook)** | [stock-market-analysis/technical-analysis/handbook/](../stock-market-analysis/technical-analysis/handbook/README.md) |
| **TA Revision & cheat sheets** | [Revision/](../Revision/) |
| **TA Book summaries** | [stock-market-analysis/technical-analysis/book-summary/](../stock-market-analysis/technical-analysis/book-summary/README.md) |
| **Fundamental Analysis** | [stock-market-analysis/fundamental-analysis/](../stock-market-analysis/fundamental-analysis/README.md) |
| **Fundamental book notes** | [stock-market-analysis/fundamental-analysis/book-notes/](../stock-market-analysis/fundamental-analysis/book-notes/README.md) |
| **Options Trading** | [stock-market-analysis/options-trading/](../stock-market-analysis/options-trading/README.md) |
| **Options book notes** | [stock-market-analysis/options-trading/book-notes/](../stock-market-analysis/options-trading/book-notes/README.md) |
| **Tips and Tricks** | [Tips_and_Tricks/](../Tips_and_Tricks/README.md) |
| **This summary folder** | [Summary/](README.md) |

---

## 6. One-Page Quick Reference

**Technical:** Structure (HH/HL, BOS) → Levels (S/R) → Pattern or indicator confirmation → Entry/stop/target → Size by risk% (1%, size = $risk / |entry−stop|).

**Fundamental:** Statements → Ratios → Valuation (DCF/multiples) → Qualitative (moat, management) → Margin of safety → Buy when price < value.

**Options:** Define view (direction/volatility) → Choose strategy (call/put/spread/straddle) → Check Greeks (delta, theta, vega) → Size and expiration → Manage or close before expiry.

---

*For discipline-specific detail, open [Technical_Analysis_Summary.md](Technical_Analysis_Summary.md), [Fundamental_Analysis_Summary.md](Fundamental_Analysis_Summary.md), and [Options_Trading_Summary.md](Options_Trading_Summary.md).*
