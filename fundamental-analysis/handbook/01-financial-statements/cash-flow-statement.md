# Cash Flow Statement

The cash flow statement tracks actual cash entering and leaving the business over a period. It is the most difficult statement to manipulate and the most reliable indicator of financial health. The famous saying holds: **"Revenue is vanity, profit is sanity, cash is reality."**

---

## Structure

The statement divides cash flows into three sections:

```
Operating Activities (OCF)
  Net Income
  + Depreciation & Amortization
  + Stock-based Compensation
  ± Changes in Working Capital
  ± Other adjustments
= Cash from Operations

Investing Activities
  − Capital Expenditures (CapEx)
  ± Acquisitions / Divestitures
  ± Purchases/sales of investments
= Cash from Investing

Financing Activities
  + Debt Issuance
  − Debt Repayment
  − Dividends Paid
  − Share Repurchases
  + Proceeds from Stock Issuance
= Cash from Financing

Net Change in Cash = OCF + Investing + Financing
Ending Cash = Beginning Cash + Net Change in Cash
```

---

## Operating Cash Flow (OCF) vs. Net Income

This is the most important comparison in all of financial statement analysis.

**Net income uses accrual accounting** — revenue is recognized when earned, expenses when incurred, regardless of when cash moves. This creates timing differences between reported earnings and actual cash flow.

**OCF is cash reality.** It starts with net income and adjusts for:

### Non-cash Add-backs

**Depreciation & Amortization (D&A)**
A non-cash expense that reduces net income but not cash. Added back to reconcile net income to cash. This is why EBITDA is higher than EBIT — D&A is added back. Capital-intensive businesses have large D&A; for them, EBITDA overstates cash earnings because the business needs to replace depreciating assets.

**Stock-Based Compensation (SBC)**
Another non-cash expense. Added back to reconcile net income to OCF. However, SBC is real dilution to shareholders. Comparing OCF to net income is misleading if SBC is large — consider subtracting SBC from OCF for a cleaner cash measure.

**Deferred Taxes**
Timing differences between book and tax accounting create deferred tax assets/liabilities. Changes in these flow through as adjustments to OCF.

### Working Capital Changes

Changes in working capital affect cash timing:

| Working Capital Item | Increase → | Decrease → |
|---------------------|-----------|-----------|
| Accounts Receivable | Uses cash (OCF −) | Releases cash (OCF +) |
| Inventory | Uses cash (OCF −) | Releases cash (OCF +) |
| Accounts Payable | Releases cash (OCF +) | Uses cash (OCF −) |
| Deferred Revenue | Releases cash (OCF +) | Uses cash (OCF −) |

**Key insight:** A company building revenue rapidly will see receivables and inventory rise, consuming working capital. OCF will temporarily lag net income. This is normal for growth. If working capital consumption persists or deepens without corresponding revenue growth, it's a concern.

---

## Why OCF and Net Income Diverge

### Legitimate Reasons (Acceptable)

- **Growth investment:** High-growth companies build inventory and extend credit to customers, widening the OCF-earnings gap temporarily.
- **Seasonality:** Retailers build inventory before holiday seasons; OCF lags in Q3, surges in Q4.
- **Large D&A relative to maintenance CapEx:** Capital-light businesses with heavily amortized acquired intangibles may show OCF well above net income.

### Problematic Reasons (Red Flags)

- **Aggressive revenue recognition:** Revenue booked before cash is received inflates earnings. If receivables consistently grow faster than revenue, the company may be pulling forward future sales.
- **Channel stuffing:** Shipping product to distributors who haven't ordered it inflates revenue today; excess inventory comes back as returns later. Receivables balloon, then get written off.
- **Capitalizing operating expenses:** Instead of expensing costs through the income statement, some companies capitalize them as assets (add to balance sheet). This lowers reported expenses, boosting net income, but CapEx on the cash flow statement rises. OCF looks fine; net income looks too good.

---

## Investing Activities

### Capital Expenditures (CapEx)

CapEx is cash spent on acquiring or upgrading long-term assets (property, equipment, technology infrastructure).

**Maintenance CapEx:** The investment required to maintain current productive capacity. Hard to isolate from reported CapEx; requires management commentary or analyst estimation.

**Growth CapEx:** Investment in new capacity to drive future revenue growth. A positive signal if returns are high; destructive if returns are below cost of capital.

**CapEx as % of Revenue** varies hugely by industry:

| Industry | Typical CapEx/Revenue |
|---------- |----------------------|
| Software / Asset-light tech | 2–5% |
| Consumer staples | 3–6% |
| Healthcare / Pharma | 5–10% |
| Manufacturing | 5–12% |
| Semiconductors | 10–20% |
| Telecom / Cable | 15–25% |
| Airlines / Rail | 15–25% |
| Oil & Gas E&P | 20–40% |

### Acquisitions and Divestitures

Cash paid for acquisitions appears as a large one-time outflow. Serial acquirers (companies that regularly buy businesses) often have volatile investing cash flows. Assess:
- Are acquisitions creating value (do acquired businesses generate returns above WACC)?
- Is the company overpaying (paying large goodwill premiums)?
- Is M&A masking organic growth deceleration?

Cash received from divestitures is a source of investing cash flow but should not be confused with operating cash generation.

### Purchases and Sales of Investments

Cash movements related to marketable securities held for investment. For most operating companies, this is minor. For companies with large cash hoards (Apple, Berkshire), these movements can be substantial.

---

## Free Cash Flow (FCF)

**FCF = Operating Cash Flow − Capital Expenditures**

FCF is the cash available to the company after maintaining and growing its asset base — the true "owner earnings." This is the most important cash flow metric for valuation.

FCF can be used for:
- Paying dividends
- Buying back shares
- Paying down debt
- Making acquisitions
- Building cash reserves

**FCF Margin = FCF / Revenue** — measures how efficiently revenue converts to free cash.

**FCF Yield = FCF / Market Capitalization** — a direct comparison to earnings yield. FCF yield >5–7% often indicates reasonable valuation (higher is better).

### FCF Variants

**Unlevered FCF (FCFF — Free Cash Flow to Firm):**
FCF before debt payments. Used in DCF valuation.
`FCFF = EBIT × (1 − Tax Rate) + D&A − Changes in Working Capital − CapEx`

**Levered FCF (FCFE — Free Cash Flow to Equity):**
FCF after interest and debt payments. What remains for equity holders.
`FCFE = Net Income + D&A − CapEx − Changes in Working Capital − Debt Repayment + New Debt Issuance`

---

## Financing Activities

### Debt Issuance and Repayment

New debt raises cash; debt repayment uses cash. Watching the debt trajectory over years reveals whether the company is deleveraging (positive) or building leverage (potentially concerning, especially in rising rate environments).

**Refinancing vs. net new debt:** Distinguish between rolling over existing debt (neutral) and adding net new debt (increases leverage).

### Dividends

Cash dividends represent a direct return to shareholders but reduce the company's cash. Sustainability of dividends should be assessed against FCF, not net income: `Dividend Coverage = FCF / Total Dividends Paid`. A ratio below 1.0 means dividends are being funded by borrowing or asset sales — unsustainable.

### Share Repurchases (Buybacks)

Cash used to repurchase shares. Buybacks are often the largest use of cash for mature US companies. Assess:
- **Price paid vs. intrinsic value:** Buybacks at depressed valuations create value; buybacks at peak valuations destroy it.
- **Net buybacks vs. gross buybacks:** Subtract SBC issuance from gross buybacks to get net share reduction. Many tech companies buy back $5B worth of shares but issue $3B in SBC — net retirement is only $2B.

### Equity Issuance

New stock sold to the public or institutions. Dilutes existing shareholders. For mature profitable companies, frequent equity issuances signal inability to fund growth internally. For early-stage companies, necessary for growth capital.

---

## Red Flags in the Cash Flow Statement

**1. Persistent net income significantly above OCF**
Over any 3–5 year period, net income and OCF should track reasonably closely (OCF is typically modestly above net income for quality businesses due to D&A add-back). A widening gap — especially if receivables or other assets are growing — is a serious warning sign.

**2. CapEx persistently below D&A (without business shrinkage explanation)**
D&A represents the economic deterioration of assets. If a company consistently spends less than D&A on CapEx, it is likely underinvesting (deferring maintenance) or the D&A is overstating asset decay. Both scenarios deserve scrutiny.

**3. Positive FCF only via working capital liquidation**
A company can generate one-time FCF by cutting inventory, collecting faster, or delaying payments — but this is not sustainable. Look at multi-year FCF trends.

**4. Heavy reliance on financing activities to fund operations**
If OCF is negative or small, and the company funds itself by repeatedly issuing debt or equity, it is burning cash on operations — only sustainable with a credible path to profitability.

**5. Divergence between operating and investing cash flows**
A company with consistently negative investing cash flow (heavy CapEx or M&A) while earning thin operating cash flow may be in a value-destroying growth trap — investing heavily without generating adequate returns.

**6. SBC as a large proportion of OCF**
If OCF is $1B but $400M of that is SBC (a non-cash add-back), true owner cash generation is only $600M. Report adjusted FCF = OCF − CapEx − SBC for capital-light technology companies.

---

## Quick Reference: Key Cash Flow Metrics

| Metric | Formula | Benchmark |
|--------|---------|-----------|
| FCF | OCF − CapEx | Positive; growing |
| FCF Margin | FCF / Revenue | >10% = capital-efficient |
| FCF Yield | FCF / Market Cap | >5% = potentially attractive |
| Cash Conversion | OCF / Net Income | >1.0 = high quality |
| CapEx/Revenue | CapEx / Revenue | Industry-specific |
| Dividend Coverage | FCF / Dividends | >1.5x = sustainable |
