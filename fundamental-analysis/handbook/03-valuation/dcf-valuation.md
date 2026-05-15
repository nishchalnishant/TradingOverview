# DCF Valuation

The Discounted Cash Flow (DCF) model estimates the intrinsic value of a business as the present value of all future free cash flows. It is theoretically the most rigorous valuation method — and the most assumption-sensitive. A DCF done well is a powerful anchor; a DCF done carelessly produces false precision.

**Core Formula:**

`Intrinsic Value = Σ [FCFt / (1 + WACC)^t] + [Terminal Value / (1 + WACC)^n]`

---

## Step-by-Step DCF Construction

### Step 1: Project Free Cash Flow (FCF)

Typical projection horizon: 5–10 years.

For each year, project:

```
Revenue
× Operating Margin
= EBIT
× (1 − Tax Rate)
= NOPAT
+ D&A
− CapEx
± Change in Working Capital
= Unlevered Free Cash Flow (FCFF)
```

**Key projection inputs:**

| Input | How to Estimate |
|-------|----------------|
| Revenue growth | Historical growth, industry growth rate, market share trends, management guidance |
| Operating margin | Historical margins, trajectory, gross margin + cost structure |
| Tax rate | Effective tax rate (normalized); adjust for NOLs if applicable |
| D&A | Often modeled as % of revenue or gross PP&E |
| CapEx | Maintenance CapEx (% of revenue) + growth CapEx |
| Working capital | Changes in DSO, DIO, DPO vs. revenue growth |

**Year-by-year FCF example (base case):**

| Year | Revenue | EBIT Margin | EBIT | NOPAT (21% tax) | D&A | CapEx | ΔNWC | FCF |
|------|---------|------------|------|-----------------|-----|-------|------|-----|
| 1 | 1,000 | 20% | 200 | 158 | 50 | (80) | (20) | 108 |
| 2 | 1,100 | 21% | 231 | 182 | 55 | (88) | (22) | 127 |
| 3 | 1,210 | 22% | 266 | 210 | 60 | (96) | (24) | 150 |
| ... | | | | | | | | |

---

### Step 2: Estimate Terminal Value

Terminal value (TV) captures the value of all cash flows beyond the explicit forecast period. It typically represents 60–80% of total DCF value — which is both its importance and its danger.

**Method 1: Gordon Growth Model (Perpetuity Growth)**

`TV = FCF_n × (1 + g) / (WACC − g)`

Where:
- FCF_n = free cash flow in the final forecast year
- g = perpetual growth rate (terminal growth rate)
- WACC = discount rate

The terminal growth rate should be conservative — typically 2–3% for a US company (roughly nominal GDP growth). Assuming 5%+ perpetual growth implies the company will eventually dwarf the entire economy.

**Method 2: Exit Multiple**

`TV = EBITDA_n × Exit Multiple`

Apply an EV/EBITDA multiple consistent with what mature companies in the industry trade at. Then discount this back to the present.

This method is more intuitive and market-grounded but circular (you're using market multiples to value the company via market multiples).

**Best practice:** Use both methods and compare. Large divergence signals that one assumption (perpetual growth rate or exit multiple) is inconsistent.

---

### Step 3: Discount at WACC

**Weighted Average Cost of Capital (WACC)**

`WACC = (E/V) × Re + (D/V) × Rd × (1 − Tax Rate)`

Where:
- E = market value of equity
- D = market value of debt
- V = E + D (total firm value)
- Re = cost of equity
- Rd = cost of debt (pre-tax yield on company debt)

**Cost of Equity via CAPM:**

`Re = Risk-Free Rate + Beta × Equity Risk Premium`

| Input | Typical Value | Source |
|-------|-------------|--------|
| Risk-Free Rate | 10-year Treasury yield (~4–5% in 2024–2025) | Bloomberg / FRED |
| Equity Risk Premium (ERP) | 4–6% (Damodaran estimates ~5%) | Damodaran.com |
| Beta | Company-specific; 0.5–2.0 for most stocks | Bloomberg, Yahoo Finance |

**Example WACC calculation:**

- Risk-free rate: 4.5%
- ERP: 5.0%
- Beta: 1.2 → Cost of equity = 4.5% + 1.2 × 5.0% = 10.5%
- Debt/Capital = 20%, Equity/Capital = 80%
- Cost of debt (pre-tax): 6%, tax rate: 21% → After-tax cost of debt = 4.74%
- **WACC = 0.80 × 10.5% + 0.20 × 4.74% = 9.35%**

**WACC nuances:**
- Use target capital structure, not current (if temporarily over/under leveraged)
- Add a **small company premium** (1–3%) for less liquid, smaller-cap stocks
- For companies in distress or with high operating uncertainty, WACC of 12–15%+ may be appropriate
- WACC is very sensitive to beta, which itself is estimated with noise

---

### Step 4: Calculate Enterprise Value and Equity Value

**Enterprise Value (EV) = PV of FCFs (years 1–n) + PV of Terminal Value**

**Equity Value = EV − Net Debt + Non-operating Assets**

Where Net Debt = Total Debt − Cash

**Intrinsic Value Per Share = Equity Value / Diluted Shares Outstanding**

---

### Step 5: Sensitivity Analysis

The most important step that most people skip. Because DCF value is so sensitive to assumptions, build a sensitivity table for at least two key variables.

**Example: WACC × Terminal Growth Rate sensitivity (intrinsic value per share)**

|  | g = 1.5% | g = 2.0% | g = 2.5% | g = 3.0% | g = 3.5% |
|--|---------|---------|---------|---------|---------|
| WACC = 8.0% | $95 | $105 | $118 | $136 | $162 |
| WACC = 9.0% | $80 | $87 | $96 | $108 | $124 |
| WACC = 10.0% | $68 | $74 | $81 | $90 | $102 |
| WACC = 11.0% | $59 | $63 | $69 | $75 | $84 |
| WACC = 12.0% | $51 | $55 | $59 | $65 | $72 |

The range of values across the table tells you how much your conclusion depends on the specific assumptions. If the stock at $70 looks cheap across most of the table, it is robustly cheap. If it only looks cheap in the top-right corner, the margin of safety is thin.

### Bull / Base / Bear Scenarios

Build three scenarios with different revenue growth rates, margin assumptions, and terminal growth:

| Scenario | Revenue CAGR | Terminal Margin | g | WACC | Intrinsic Value |
|---------|-------------|----------------|---|------|----------------|
| Bull | 15% | 25% | 3% | 9% | $120 |
| Base | 10% | 20% | 2.5% | 10% | $85 |
| Bear | 5% | 15% | 1.5% | 11% | $50 |

Assign probabilities to each (e.g., 25% / 50% / 25%) to get a probability-weighted value.

---

## Key Assumptions That Drive Value

### Revenue Growth Rate

The single most impactful assumption. A 2% difference in long-term revenue growth can change the DCF value by 30–50%.

Ask:
- What is the total addressable market (TAM) and how penetrated is the company?
- Is the company a share taker or mature player?
- Are there structural headwinds (industry disruption, regulation)?

### Operating Margins

Model margins to a normalized target. Avoid assuming today's temporarily high margins persist forever, or that temporarily depressed margins never recover.

Consider: does the business have operating leverage (margins should expand with revenue growth) or is it a fixed-margin business?

### CapEx and Reinvestment

High-growth DCF value depends on reinvestment — the company must invest capital to grow. Neglecting this overstates value. The "reinvestment rate" is:

`Reinvestment Rate = (CapEx − D&A + ΔNWC) / NOPAT`

A company growing at 10% but reinvesting 80% of NOPAT has less FCF than one growing at 6% but reinvesting 40% of NOPAT.

### WACC

A 1% change in WACC can change DCF value by 15–25%. Given the uncertainty in estimating WACC (especially beta), treat WACC as a range, not a point estimate.

---

## Common DCF Mistakes

**1. Perpetually high growth rates**
Assuming 10%+ revenue growth forever. Economic reality and competition compress margins and growth over time. Even the best businesses eventually revert toward GDP growth.

**2. Ignoring mean reversion of margins**
Assuming today's peak margins persist indefinitely. High ROIC businesses attract competition; margins typically compress over 5–10 years unless the moat is exceptional.

**3. Underestimating risk (too low WACC)**
Using low WACCs because interest rates are low, without adjusting equity risk premium. A low WACC inflates value; be conservative.

**4. Neglecting dilution**
Failing to account for ongoing stock-based compensation as a real cost. Future FCF effectively belongs to fewer shareholders than today's.

**5. Anchoring to current multiples for terminal value**
If current EV/EBITDA multiples are at a cyclical peak, using them as the exit multiple bakes in an optimistic assumption.

**6. Treating terminal value as certain**
Terminal value is often 70%+ of total DCF value. It is a mathematical convenience for infinite cash flows, not a certainty. Any model where >80% of value is in terminal value is essentially a faith-based exercise.

**7. Not doing sensitivity analysis**
A single point estimate is nearly useless. Always stress-test at minimum WACC and terminal growth.
