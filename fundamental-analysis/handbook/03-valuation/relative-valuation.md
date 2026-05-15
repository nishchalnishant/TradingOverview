# Relative Valuation

Relative valuation (also called "comps") values a company by comparing it to similar businesses — peers in the public market (trading comps) or prior M&A transactions (transaction comps). The underlying logic: **similar assets should trade at similar prices.**

This is the dominant valuation method used in investment banking, equity research, and trading because it is fast, market-grounded, and doesn't require building a full DCF. But it is only as good as the quality of your comparable set.

---

## Comparable Company Analysis (Trading Comps)

### Purpose

Comparable companies analysis answers: "Given what the market is paying for similar businesses, what should this company be worth?"

It anchors value to current market reality — useful because it captures the current risk appetite, interest rate environment, and sector sentiment. The weakness: if all comps are overvalued (or undervalued), the analysis inherits that mispricing.

### How to Build a Comps Set

**Step 1: Define the peer group**

Start with the company's own stated competitors (10-K, investor presentations). Then expand to:

- Same industry and sub-industry classification (GICS, SIC codes)
- Similar business model (not just sector — a pure-play SaaS company shouldn't be comped to a diversified tech conglomerate)
- Similar size (market cap within 0.3x–3.0x of the subject)
- Similar growth profile (comparable revenue growth rates)
- Similar profitability (comparable margins or similar stage of development)

**Peer group criteria checklist:**

| Criterion | Why It Matters |
|-----------|---------------|
| Same end market | Demand dynamics are comparable |
| Similar gross margin | Pricing power is similar |
| Similar growth rate | Market is valuing comparable forward earnings |
| Similar capital intensity | CapEx / balance sheet affects FCF multiples |
| Similar geography | Country risk, tax rate, regulatory environment |

Be willing to use 4–8 tight peers rather than 15–20 loose ones. More comps ≠ better analysis.

**Step 2: Spread the multiples**

For each comparable company, calculate:

| Multiple | Formula |
|----------|---------|
| EV/LTM Revenue | EV / Last twelve months revenue |
| EV/NTM Revenue | EV / Next twelve months revenue (consensus) |
| EV/LTM EBITDA | EV / LTM EBITDA |
| EV/NTM EBITDA | EV / NTM EBITDA |
| P/E (LTM) | Price / LTM EPS |
| P/E (NTM) | Price / NTM EPS |
| P/FCF | Price / FCF per share |

**Use NTM (forward) multiples when:**
- The company is growing rapidly (LTM understates current scale)
- Comparing companies at different stages (LTM margins distorted by recent investments)

**Use LTM (trailing) multiples when:**
- Guidance visibility is low
- Comparing stable mature businesses

**Step 3: Calculate statistical measures**

For each multiple across the peer set:
- Minimum, Maximum
- 25th percentile, 75th percentile
- Median (preferred over mean — less sensitive to outliers)
- Mean

**Step 4: Apply the multiple range**

Decide where your subject company falls in the distribution — at a discount, at the median, or at a premium — and apply the relevant multiple range to the subject's financials.

`Implied EV = Subject's EBITDA × Multiple Range`
`Implied Equity Value = EV − Net Debt`
`Implied Share Price = Equity Value / Diluted Shares`

**Step 5: Reconcile to a value**

Produce a "football field" showing the implied value ranges from different multiples. The overlap of multiple methods gives you the central estimate.

---

### Adjusting for Differences Between Companies

Peers are never perfectly comparable. Adjust your thinking (or the multiples) for:

| Difference | Adjustment |
|-----------|-----------|
| Higher growth than peers | Justify premium to median multiple |
| Lower margin than peers | Discount; or use forward margins at maturity |
| Higher leverage than peers | EV multiples unaffected, but equity value is compressed |
| One-time item inflated earnings | Normalize the earnings base before applying multiple |
| Different geographic mix | Adjust for country risk premium differences |
| Acquisitive (goodwill-heavy) | Be cautious of EV/EBITDA if amortization is being added back and acquired businesses aren't performing |

---

## Precedent Transactions Analysis

Precedent transactions ("deal comps" or "transaction comps") value a company based on what acquirers paid for similar businesses in prior M&A deals.

### Why Transaction Comps Differ from Trading Comps

Acquirers pay a **control premium** — the extra amount above the current market price needed to gain majority control and execute a deal. Historically, control premiums average 20–40% over pre-announcement stock price.

Transaction comps are used to:
- Estimate acquisition value for M&A advisory work
- Anchor the "bull case" value in an investment thesis
- Set price targets in situations where M&A is a realistic catalyst

### How to Build Transaction Comps

**Step 1: Find relevant transactions**

Sources: Bloomberg M&A database, S&P Capital IQ, public company press releases (8-Ks), news searches. Filter for:
- Same industry/sub-industry
- Comparable deal size
- Recent enough to be relevant (past 3–5 years preferred; markets change)
- Sufficient public disclosure to calculate multiples

**Step 2: Calculate transaction multiples**

| Metric | Formula |
|--------|---------|
| EV/LTM Revenue | Transaction EV / Target's LTM Revenue |
| EV/LTM EBITDA | Transaction EV / Target's LTM EBITDA |
| P/E | Transaction price per share / LTM EPS |
| Premium to unaffected price | (Deal Price − Pre-announcement price) / Pre-announcement price |

**Transaction EV = Deal equity value + assumed debt − assumed cash**

Note: Transaction EV is based on the negotiated deal price, not the stock price.

**Step 3: Interpret the range**

Transaction multiples are typically 15–40% above trading comps due to:
- Control premium
- Synergy expectations (acquirer can pay more because combined entity is worth more)
- Competitive bidding in some processes

If your subject company trades well below comparable acquisition multiples, it may be an M&A candidate.

---

## When to Use Each Multiple

### EV/EBITDA

**Best for:** Capital-intensive businesses, companies with significant debt, M&A analysis, cross-capital-structure comparisons.

**Avoid for:** High-CapEx businesses where EBITDA overstates cash generation (EBITDA ignores CapEx). A cable company with 80% EBITDA margins still has massive CapEx needs.

### P/E

**Best for:** Profitable, relatively stable businesses; consumer-facing comparisons where EPS is the standard metric.

**Avoid for:** Companies with negative earnings, heavily leveraged companies (interest expense distorts), cyclical companies at earnings peaks.

### EV/Revenue (EV/Sales)

**Best for:** Pre-profit or low-margin businesses; SaaS and high-growth technology; turnaround situations.

**Avoid for:** Businesses where margins vary dramatically (a 3% margin retailer and 25% margin software company should not trade at the same EV/Revenue).

### P/B (Price-to-Book)

**Best for:** Banks, insurance companies, asset managers, real estate companies where assets are marked to market and book value is economically meaningful.

**Avoid for:** Asset-light businesses (technology, services) where internally developed intangibles are not capitalized.

### P/FCF

**Best for:** Capital-light, FCF-generative businesses; comparing cash yield across different capital structures.

**Avoid for:** Capital-intensive businesses with lumpy CapEx cycles; high-growth companies reinvesting heavily.

---

## Pitfalls in Relative Valuation

**1. Comparing apples to oranges**
The most common error. A cloud software company and a legacy on-premise software company are both "software" but have dramatically different business model economics.

**2. Circular reasoning**
If you're trying to decide if the market is wrong about a stock, comparing it to how the market values peers doesn't help — it just tells you if the market is consistently wrong. Comps work for relative value but not absolute value.

**3. Survivorship bias in transaction comps**
You only see completed deals. Failed or cancelled acquisitions are underrepresented, which may overstate typical deal terms.

**4. Stale comparables**
Transaction comps from 5+ years ago may reflect a completely different interest rate and sentiment environment. M&A multiples paid at 2021 peak rates may be irrelevant in a 5% interest rate world.

**5. Adjusting too liberally**
Adding backs and adjustments to make a company look comparable to higher-quality peers is a common analytical mistake. If a company's EBITDA margin is lower because the business is structurally inferior, that is real — don't adjust it away.

**6. Ignoring capital allocation quality**
Two companies at identical EV/EBITDA multiples can have very different intrinsic values if one reinvests at ROIC > WACC and the other destroys capital. Comps don't capture management quality.
