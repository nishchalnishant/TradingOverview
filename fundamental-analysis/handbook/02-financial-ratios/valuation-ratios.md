# Valuation Ratios

Valuation ratios compare market price to a measure of the company's fundamental value — earnings, book value, cash flow, or revenue. They answer: **how much is the market paying for this business, and is that reasonable?**

No single multiple is universally correct. The right metric depends on the business type, stage, and industry.

---

## Equity-Based Multiples (Price / X)

These multiples use **market capitalization** (stock price × shares outstanding) in the numerator. They measure what equity investors are paying per unit of earnings, book value, or revenue.

### Price-to-Earnings (P/E)

**P/E = Stock Price / Earnings Per Share = Market Cap / Net Income**

The most widely used valuation metric.

**Trailing P/E (TTM):** Uses the last 12 months of actual earnings. Based on known data; backward-looking.

**Forward P/E:** Uses the next 12 months of consensus analyst earnings estimates. Forward-looking but depends on estimate accuracy.

**Normalized P/E:** Uses earnings smoothed over a business cycle (typically 5–7 years) or adjusted for non-recurring items. Removes distortion from cyclical peaks/troughs and one-time charges. Also called "Shiller P/E" at the market level.

**When to use P/E:**
- Profitable, mature companies with stable earnings
- Cross-company comparisons within the same industry
- Not useful for: companies with negative or near-zero earnings, highly cyclical businesses at earnings peaks (P/E looks deceptively low)

**Interpretation:**

| P/E Range | Context |
|-----------|---------|
| <10x | Possibly cheap; or earnings declining, high risk, or cyclical peak |
| 10–15x | Historically average for mature, slow-growth companies |
| 15–25x | Moderate growth; or quality premium |
| 25–40x | High growth expectations baked in |
| >40x | Very high growth expected or speculative premium |

**Pitfall — Cyclical companies:** A steel company at the top of a commodities cycle may report very high earnings, giving a seemingly low P/E (5–8x). This is a trap — earnings are unsustainably high. Use normalized/through-cycle earnings for cyclicals.

### Price-to-Book (P/B)

**P/B = Stock Price / Book Value Per Share = Market Cap / Shareholders' Equity**

What it measures: What the market pays for each dollar of accounting equity.

**When to use P/B:**
- Financial companies (banks, insurers) where assets are marked to market and book value is meaningful
- Asset-heavy businesses where balance sheet value approximates replacement cost
- Distressed situations where liquidation value matters
- Not useful for: asset-light businesses (software, brands) where intangibles are not capitalized

**Interpretation:**
- P/B <1.0: Market pricing the company below liquidation value — either a bargain or a value trap (if assets are impaired)
- P/B 1–2x: Typical for low-ROE, capital-heavy businesses
- P/B 3–10x+: Typical for high-ROE, capital-light businesses (Visa, MSCI)

**P/B and ROE Connection:**
The P/B multiple that a business deserves is directly related to its ROE. A business earning 20% ROE on its equity "deserves" a higher P/B than one earning 8%. The Gordon Growth Model implies:

`Justified P/B = (ROE − g) / (Cost of Equity − g)`

Where g = sustainable growth rate. This framework shows that high P/B multiples are justified when ROE significantly exceeds the cost of equity.

### Price-to-Sales (P/S)

**P/S = Market Cap / Revenue**

**When to use P/S:**
- Pre-profit or low-margin businesses where P/E is meaningless
- High-growth companies where current earnings understate the mature earnings power
- Businesses with temporarily depressed margins (turnarounds)
- SaaS companies where the focus is on ARR growth

**Limitation:** P/S ignores profitability entirely. A company with 3% margins should trade at a much lower P/S than one with 30% margins, all else equal.

**Normalized P/S → Implied Margin Check:**
If a company trades at 10x P/S and comparable mature businesses earn 20% net margins, the implied P/E at maturity is ~50x — which requires either very fast growth to justify or is simply expensive.

### Price-to-Free Cash Flow (P/FCF)

**P/FCF = Market Cap / Free Cash Flow**

Where FCF = Operating Cash Flow − CapEx.

What it measures: What investors pay for each dollar of distributable cash flow — arguably the most important equity valuation multiple.

**Advantages over P/E:**
- Not affected by accounting choices (D&A policy, revenue recognition)
- Includes CapEx reality (P/E ignores that CapEx exceeds D&A for growing businesses)
- Harder to manipulate than earnings

**Typical ranges:**
- P/FCF of 15–20x: Fair value for moderate-growth, capital-light business
- P/FCF <15x: Potentially cheap, especially for quality businesses
- P/FCF >30x: High growth required to justify

**Caution:** FCF can be temporarily depressed by growth CapEx. Normalize CapEx (separate maintenance from growth CapEx) before applying P/FCF.

---

## Enterprise Value Multiples (EV / X)

**Enterprise Value (EV) = Market Cap + Total Debt − Cash**

EV represents the total value of the business to all capital providers (equity and debt). It is acquisition price — what you'd pay to buy the entire company and pay off all debt.

EV multiples are preferred over equity multiples for:
1. Comparing companies with different capital structures
2. Acquisition analysis
3. Any situation where leverage significantly differs between companies

### EV/EBITDA

**EV/EBITDA = Enterprise Value / EBITDA**

EBITDA = EBIT + Depreciation + Amortization

The most commonly used valuation multiple in investment banking and M&A. EBITDA approximates operating cash flow before working capital changes — making it useful for cross-capital-structure comparisons.

**Typical ranges by sector:**

| Sector | Typical EV/EBITDA |
|--------|-----------------:|
| Software (SaaS) | 15–40x |
| Consumer staples | 12–18x |
| Healthcare services | 10–16x |
| Industrials | 8–12x |
| Telecom | 6–10x |
| Basic materials | 5–8x |
| Energy | 4–7x |

**Limitation:** EBITDA ignores CapEx. For capital-intensive businesses, EV/EBITDA overstates free cash yield because significant cash must be reinvested. Use EV/EBIT or EV/FCF for capex-heavy businesses.

### EV/EBIT

**EV/EBIT = Enterprise Value / EBIT**

More conservative than EV/EBITDA because it includes depreciation — better for capital-intensive businesses where depreciation is a real economic cost (assets actually wear out and must be replaced).

Use EV/EBIT when D&A is high relative to CapEx (asset-heavy businesses where D&A tracks actual asset consumption).

### EV/Revenue (EV/Sales)

**EV/Revenue = Enterprise Value / Revenue**

Use when:
- Company is pre-profit or early-stage
- Revenue is the primary growth metric being valued
- Comparing across businesses with different capital structures (better than P/S in this respect)

For high-growth SaaS companies, EV/Forward Revenue (next twelve months) is the standard metric — traders watch whether a company is pricing at a premium or discount to its peer cohort's revenue multiple.

---

## PEG Ratio (For Growth Stocks)

**PEG = P/E Ratio / Annual EPS Growth Rate**

Peter Lynch popularized PEG. The idea: a P/E of 20x is "fair" if the company is growing EPS at 20% per year; a P/E of 30x is expensive at 20% growth (PEG = 1.5).

**Interpretation:**
- PEG < 1.0: Potentially undervalued relative to growth
- PEG = 1.0: Growth and valuation roughly balanced (Lynch's "fair value")
- PEG > 1.5–2.0: Expensive relative to growth

**Limitations:**
- Which growth rate? EPS growth can differ from revenue growth, cash flow growth
- Short-term growth rates are volatile and hard to forecast
- Ignores risk — two companies growing at 20% with different risk profiles should have different P/Es
- Ignores the starting margin level — high P/E with low growth rate can be appropriate for extremely high-quality businesses (compounders)

Use PEG as a rough filter to flag expensive-looking stocks that might actually be reasonable given growth, or "cheap" stocks that are actually overpriced relative to stagnant earnings.

---

## When to Use Each Multiple

| Multiple | Best For | Avoid When |
|----------|---------|-----------|
| P/E (Trailing) | Stable, mature companies | Cyclical peaks, negative earnings |
| P/E (Forward) | Growth companies with visible earnings | Guidance uncertainty |
| P/B | Banks, insurance, asset-heavy businesses | Capital-light, IP-driven |
| P/S | Pre-profit growth companies, turnarounds | Commodities (margins vary too much) |
| P/FCF | Capital-light, FCF-generative businesses | Heavy growth CapEx years |
| EV/EBITDA | M&A analysis, cross-leverage comparisons | Capital-intensive (CapEx > D&A) |
| EV/EBIT | Capital-intensive businesses | Pre-profit companies |
| EV/Revenue | Early-stage, high-growth, cross-leverage | Low-margin commodities |
| PEG | Growth stock screening | Mature/value companies |

---

## Adjustments for Risk and Growth

Two companies with the same P/E should not trade at the same P/E if one is growing faster or has lower risk.

**Discount for:**
- High leverage (leveraged FCF more volatile)
- Cyclical earnings (may be near-peak)
- Single-product dependence
- Customer concentration
- Regulatory risk

**Premium for:**
- Durable competitive advantage (moat)
- Capital-light model with high ROIC
- Long runway for growth
- Recurring revenue (subscription, annuity-like)
- Strong management capital allocation record
