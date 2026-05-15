# Earnings Quality

Earnings quality measures the degree to which reported earnings accurately reflect the sustainable, underlying economics of the business. High-quality earnings are repeatable, backed by cash flow, and free from accounting distortion. Low-quality earnings require increasing amounts of accounting creativity to maintain their appearance — a house of cards that eventually collapses.

---

## The Accruals Concept

### What Are Accruals?

Accrual accounting recognizes revenue and expenses when they are earned/incurred, not when cash moves. This creates a timing difference between reported earnings and cash flow.

**Net Income = Operating Cash Flow − Total Accruals** (simplified)

**Accruals = Net Income − Operating Cash Flow**

When accruals are large and positive (net income >> OCF), it means reported earnings are running ahead of cash reality. When negative (OCF >> net income), cash generation is better than reported earnings suggest.

### The Sloan Accrual Anomaly

Richard Sloan (1996) documented that companies with high accruals (earnings >> cash flow) systematically underperform, while companies with low accruals (OCF >> earnings) outperform. This is because the market over-weights reported earnings and under-weights cash flow information.

**Accruals Ratio:**

`Accruals Ratio = (Net Income − OCF) / Average Total Assets`

- High positive ratio (>5–10%): Red flag; earnings quality deteriorating
- Near zero or negative: Healthy; cash flow matches or exceeds reported earnings

---

## Cash Conversion: The Primary Quality Test

**Cash Conversion Ratio = Operating Cash Flow / Net Income**

| Ratio | Interpretation |
|-------|---------------|
| >1.2 | High quality — cash exceeds reported earnings (conservative accounting or non-cash charges) |
| 0.9–1.2 | Normal range — typical D&A add-backs minus working capital changes |
| 0.6–0.9 | Moderate concern — investigate why cash lags earnings |
| <0.6 | Serious concern — persistent earnings-cash divergence; investigate immediately |

**Note:** A single year of low cash conversion can be explained by working capital build (e.g., rapid growth). Three or more consecutive years of sub-0.7 cash conversion is a major warning sign.

**Track the trend.** A declining cash conversion ratio over several years is more alarming than a single low year.

---

## Revenue Recognition Red Flags

Revenue recognition is the most common area of accounting manipulation because it directly inflates the top line — and therefore earnings.

### Channel Stuffing

**What it is:** Shipping excess inventory to distributors or retailers before it has been ordered, in order to recognize revenue sooner. The distributor may have a right of return or will return excess product in the next period.

**How to detect:**
- Accounts receivable growing significantly faster than revenue
- DSO rising quarter-over-quarter
- Revenue growth inconsistent with distributors' own reported sell-through data
- Sudden revenue reversal or "returns" in subsequent quarters

**Examples:** Several pharmaceutical and consumer goods companies have faced SEC enforcement for channel stuffing. The revenue eventually reverses when distributors return or stop ordering.

### Bill-and-Hold

**What it is:** Recording revenue for goods that have been invoiced (billed) but not yet shipped (held at the seller's warehouse). The buyer may not have even agreed to terms yet.

**Requirements for legitimacy:** Bill-and-hold is permitted under GAAP only when very specific criteria are met — the buyer requested it, the goods are separately identified, and the goods are ready for delivery. Many companies abuse this.

**How to detect:**
- Unusual spike in revenue at quarter-end
- Management discussion of "bill-and-hold arrangements" in footnotes
- AR rising without corresponding inventory decline

### Aggressive Percentage-of-Completion

**What it is:** Long-term contracts (construction, defense, IT services) recognize revenue as work is completed. Management can manipulate the estimated completion percentage to pull forward revenue.

**How to detect:**
- Project cost overruns that appear late in the project (earlier estimates were too optimistic)
- Large adjustments to prior-period revenue estimates
- Compare estimated vs. actual margin on completed projects

### Premature Revenue Recognition (SaaS / Subscription)

Subscription companies recognize revenue ratably over the contract period. Manipulators may:
- Front-load multi-year contracts incorrectly
- Include hardware as a separate performance obligation to recognize more revenue upfront
- Discount heavily at quarter-end to close deals (affecting quality of bookings)

**How to detect:**
- Deferred revenue declining unexpectedly (burning through backlog)
- Billings (cash collected) growing slower than recognized revenue
- Rule of 40 deteriorating: Revenue growth % + FCF margin % <40% despite strong reported revenue

---

## Expense Manipulation

### Capitalizing Operating Expenses

Companies can choose to capitalize certain costs (add them to the balance sheet as assets) rather than expense them immediately. This boosts current-period earnings at the expense of future depreciation charges.

**Legitimate capitalization:** Software development costs after technological feasibility, PP&E, major facility improvements.

**Aggressive capitalization:**
- Internal software costs expensed by peers but capitalized by the subject company
- Customer acquisition costs (CAC) capitalized over customer lifetime (reasonable in concept, manipulable in practice)
- Maintenance costs reclassified as improvements

**How to detect:**
- Capitalized software / intangible assets growing faster than revenue without corresponding revenue increase
- Depreciation and amortization rising rapidly as prior capitalizations are amortized
- CapEx well above industry norms relative to revenue (some is just growth investment, but persistent excess is a flag)

### Cookie Jar Reserves

**What it is:** Setting up excessive accruals or reserves during good years ("filling the cookie jar"), then releasing them during bad years to smooth earnings. The excess reserves are reversed through income, artificially supporting earnings.

**Common reserve types used:** Warranty reserves, bad debt allowances, litigation reserves, restructuring accruals.

**How to detect:**
- Sudden reversal of reserves during a weak earnings quarter that happens to produce an in-line result
- Large "gain" from reversal of prior-period accruals
- Management consistently under-providing for bad debts, then writing them off in lumpy batches

### Accelerated vs. Deferred Revenue Recognition (GAAP Flexibility)

Under ASC 606 (new revenue standard), companies have discretion in how they allocate transaction prices across performance obligations. Aggressive companies allocate more value to items recognized earlier; conservative companies allocate more to deferred recognition.

---

## Altman Z-Score: Distress Prediction

See [liquidity-leverage-ratios.md](../02-financial-ratios/liquidity-leverage-ratios.md) for the formula. The Z-Score combines balance sheet and income statement metrics to predict bankruptcy probability.

**Earnings quality context:** Companies with deteriorating Z-Scores often have earnings quality problems — they are sustaining earnings appearance while the underlying financial position weakens. The cash flow statement reveals this before the income statement does.

---

## Beneish M-Score: Manipulation Detection

The Beneish M-Score is an eight-factor model that uses financial ratios to estimate the probability that a company has manipulated its earnings.

**The Eight Variables:**

| Variable | Formula | Manipulation Signal |
|----------|---------|-------------------|
| DSRI (Days Sales Receivable Index) | (AR_t/Rev_t) / (AR_{t-1}/Rev_{t-1}) | DSRI >1 → AR growing faster than revenue |
| GMI (Gross Margin Index) | GM_{t-1} / GM_t | GMI >1 → margins deteriorating |
| AQI (Asset Quality Index) | (1 − (CA + PPE)/TA)_t / same_{t-1} | AQI >1 → more capitalized intangibles |
| SGI (Sales Growth Index) | Rev_t / Rev_{t-1} | High growth firms at more manipulation risk |
| DEPI (Depreciation Index) | Depr rate_{t-1} / Depr rate_t | DEPI >1 → depreciation rate slowing |
| SGAI (SG&A Index) | (SGA/Rev)_t / (SGA/Rev)_{t-1} | SGAI >1 → SG&A leverage worsening |
| LVGI (Leverage Index) | Leverage_t / Leverage_{t-1} | LVGI >1 → leverage increasing |
| TATA (Total Accruals to Total Assets) | (Net Income − OCF) / Total Assets | High positive = high accruals |

**M-Score Formula:**
`M = −4.84 + 0.92×DSRI + 0.528×GMI + 0.404×AQI + 0.892×SGI + 0.115×DEPI − 0.172×SGAI + 4.679×TATA − 0.327×LVGI`

**Interpretation:**
| M-Score | Probability of Manipulation |
|---------|---------------------------|
| M > −1.78 | High probability — strong manipulation signal |
| −2.22 < M < −1.78 | Gray zone — warrants investigation |
| M < −2.22 | Low probability of manipulation |

The M-Score correctly flagged Enron as a manipulator before the bankruptcy. Not every company with a high M-Score is manipulating — it is a screening tool that warrants further investigation.

---

## Normalized EPS vs. Reported EPS

**Reported EPS** includes all items — one-time gains/charges, restructuring, impairments, accounting changes.

**Adjusted/Normalized EPS** excludes non-recurring items to show sustainable earning power.

**Common adjustments:**
- Add back: restructuring charges, impairment charges, acquisition costs, legal settlements, executive severance
- Remove: one-time gains from asset sales, tax benefits from unusual items

**The key question:** Is the adjustment genuinely non-recurring, or is the company systematically excluding real costs?

**"Recurring non-recurring" items:** If a company takes restructuring charges 5 years in a row, they are not non-recurring — they reflect normal business operations being excluded from adjusted EPS. Treat multi-year "one-time" charges as recurring expenses.

**SBC in adjusted EPS:** Most technology companies exclude SBC from adjusted EPS. This is intellectually dishonest — SBC is a real cost to shareholders (dilution). True normalized earnings should include SBC as an expense.

---

## Quick Checklist: Earnings Quality

- [ ] Cash conversion ratio (OCF / Net Income): is it >0.9? Trending?
- [ ] Receivables growing faster than revenue? (DSO rising)
- [ ] Inventory growing faster than COGS? (DIO rising)
- [ ] Accruals ratio (NI − OCF) / Assets: above 5–10%?
- [ ] Revenue recognition policies consistent with industry peers?
- [ ] Are "non-recurring" charges actually recurring?
- [ ] Is SBC included in the cost base for true earnings assessment?
- [ ] Has the auditor or CFO changed recently without clear explanation?
- [ ] Beneish M-Score: above −1.78?
- [ ] Altman Z-Score: below 1.81?
