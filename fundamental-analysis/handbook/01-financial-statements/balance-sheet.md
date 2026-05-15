# Balance Sheet

The balance sheet is a snapshot of a company's financial position at a specific point in time. It answers: **what does the company own, what does it owe, and what belongs to shareholders?**

**The fundamental equation: Assets = Liabilities + Shareholders' Equity**

Everything on the left side (assets) is financed by either debt (liabilities) or equity. This equation must always balance.

---

## Structure Overview

```
ASSETS                              LIABILITIES & EQUITY
─────────────────────────────       ────────────────────────────────
Current Assets                      Current Liabilities
  Cash & Equivalents                  Accounts Payable
  Short-term Investments              Accrued Expenses
  Accounts Receivable                 Short-term Debt
  Inventory                           Deferred Revenue (current)
  Prepaid Expenses
                                    Long-term Liabilities
Non-current Assets                    Long-term Debt
  PP&E (net)                          Deferred Tax Liabilities
  Goodwill                            Pension Obligations
  Intangible Assets                   Lease Obligations
  Long-term Investments
  Deferred Tax Assets               Shareholders' Equity
                                      Common Stock + APIC
                                      Retained Earnings
                                      Treasury Stock
                                      AOCI
```

---

## Assets

### Current Assets

Assets expected to be converted to cash or used within 12 months.

**Cash and Cash Equivalents**
The most liquid asset — money in bank accounts plus short-term instruments (T-bills, money market funds) with maturities under 90 days. Large cash balances provide optionality (acquisitions, buybacks, debt paydown) but can also signal management's inability to deploy capital productively.

**Short-term Investments**
Marketable securities held for near-term liquidity. Mostly government bonds or investment-grade credit. Included in "net cash" calculations.

**Accounts Receivable (AR)**
Money owed by customers for goods/services already delivered. Reported net of allowances for doubtful accounts (estimated bad debts).

- **Days Sales Outstanding (DSO) = AR / (Revenue / 365):** Measures how quickly the company collects from customers. Rising DSO means either slower collections or aggressive revenue recognition.
- Compare DSO to peers and track the trend. A sudden increase in AR relative to revenue is a classic early warning sign.

**Inventory**
Raw materials, work-in-progress, and finished goods not yet sold.

- **Days Inventory Outstanding (DIO) = Inventory / (COGS / 365):** Measures how long inventory sits before being sold. Rising DIO can mean demand is weakening or the company is overstocking.
- **Inventory write-downs** appear as charges on the income statement when inventory becomes obsolete. Significant write-downs signal prior demand misjudgments.
- Accounting method matters: **FIFO** (first in, first out) produces lower COGS in inflationary environments, inflating earnings vs. **LIFO** (last in, first out). US GAAP allows both; IFRS only allows FIFO.

**Prepaid Expenses**
Costs paid in advance (insurance, rent deposits). Minor in most cases.

### Non-Current Assets

Assets expected to provide benefits beyond 12 months.

**Property, Plant & Equipment (PP&E)**
Physical assets used in operations: land, buildings, machinery, vehicles, equipment.

Reported net of accumulated depreciation:
**Net PP&E = Gross PP&E − Accumulated Depreciation**

Key considerations:
- High net PP&E relative to gross PP&E means assets are relatively new (or underdepriated).
- Low net/gross ratio signals aging assets that may require heavy future CapEx.
- Capital-intensive businesses (manufacturing, utilities, airlines) have large PP&E relative to earnings; capital-light businesses (software, asset managers) have minimal PP&E.

**Goodwill**
The premium paid in acquisitions above the fair value of net identifiable assets. Goodwill is only created through M&A — it never appears organically.

Under GAAP/IFRS, goodwill is not amortized but is subject to annual impairment testing. If the acquired business performs below expectations, goodwill is written down through an impairment charge on the income statement.

- **Goodwill as % of Total Assets:** A high percentage (>30–40%) means the company's book value depends heavily on M&A assumptions that may prove overly optimistic.
- Serial acquirers often carry large goodwill balances; track whether past acquisitions have ever triggered impairments.

**Intangible Assets**
Identifiable non-physical assets: patents, trademarks, customer relationships, software, licenses. These are often acquired via M&A and amortized over useful life.

**Self-developed intangibles** (e.g., internally built brands) are not capitalized under US GAAP — this makes brand-heavy consumer companies appear to have lower asset bases than acquisition-heavy competitors.

**Long-term Investments**
Equity stakes in other companies (accounted via equity method if 20–50% ownership; consolidated if >50%).

**Deferred Tax Assets (DTA)**
Future tax benefits — e.g., net operating loss carryforwards (NOLs) from prior losses that can offset future taxes. Large DTAs can be valuable (like prepaid tax) but only if the company generates taxable income to use them.

---

## Liabilities

### Current Liabilities

Obligations due within 12 months.

**Accounts Payable (AP)**
Money owed to suppliers for goods/services received but not yet paid.

- **Days Payable Outstanding (DPO) = AP / (COGS / 365):** Higher DPO means the company takes longer to pay suppliers — can indicate strong bargaining power (Walmart famously has high DPO) or financial stress.
- Rising DPO can temporarily boost free cash flow by delaying cash outflows — distinguish between structural payable leverage vs. cash management desperation.

**Accrued Expenses**
Liabilities recognized for costs incurred but not yet paid (wages, utilities, accrued bonuses). Standard operating items.

**Short-term Debt / Current Portion of Long-term Debt**
Debt maturing within 12 months. Large amounts of short-term debt in a rising rate environment or during credit tightening is a liquidity risk — can the company refinance or repay?

**Deferred Revenue**
Cash received from customers for services not yet delivered. A liability because the company still owes the service. Common in subscription businesses (SaaS, media).

**Note:** Deferred revenue is a high-quality liability — it represents future revenue that will be recognized with minimal incremental cost. Companies with growing deferred revenue have strong future revenue visibility.

### Long-Term Liabilities

**Long-term Debt**
Bonds, term loans, revolving credit facilities, and other borrowings maturing beyond 12 months. Key inputs: principal amount, maturity schedule, interest rate (fixed vs. floating), covenants.

**Deferred Tax Liabilities (DTL)**
Future tax obligations. Common when book depreciation is slower than tax depreciation (accelerated depreciation for tax creates a timing difference).

**Pension and Post-retirement Obligations**
Defined benefit pension plans create large, often underfunded liabilities. The funded status (plan assets minus projected benefit obligation) can swing significantly with interest rate and market assumptions. Large pension underfunding is often under-appreciated by the market.

**Operating Lease Obligations**
Since ASC 842 / IFRS 16 (2019), operating leases appear on the balance sheet as a right-of-use asset and corresponding lease liability. Understand this when comparing pre- and post-2019 financial statements.

**Off-Balance-Sheet Liabilities (Red Flag)**
Items that don't appear on the balance sheet but represent real financial obligations:
- Operating leases (pre-2019, now required on balance sheet)
- Contingent liabilities (litigation, warranties) — often only in footnotes
- Securitized receivables removed from the balance sheet
- Variable interest entity (VIE) structures used to keep liabilities off-balance-sheet

Always read footnotes on commitments and contingencies.

---

## Shareholders' Equity

**Common Stock + Additional Paid-in Capital (APIC)**
Proceeds from issuing equity. Common stock at par value is nominal; APIC is the excess above par.

**Retained Earnings**
Cumulative net income minus dividends paid since the company's founding. The single largest component of equity for mature companies. A company with decades of retained earnings has proven it generates persistent profits.

**Treasury Stock**
Shares repurchased and held. Reduces equity (negative entry). Large treasury stock balances relative to outstanding market cap reflect sustained buyback programs.

**Accumulated Other Comprehensive Income (AOCI)**
Unrealized gains/losses on items not run through the income statement: pension adjustments, foreign currency translation, unrealized gains/losses on available-for-sale securities.

---

## Key Balance Sheet Metrics

### Working Capital

**Working Capital = Current Assets − Current Liabilities**

Positive working capital means the company can cover short-term obligations with short-term assets. Negative working capital can be fine for subscription businesses (Amazon-style retail) or financial businesses — but for most companies it signals short-term liquidity risk.

### Book Value

**Book Value = Total Shareholders' Equity**

**Book Value Per Share = Total Equity / Diluted Shares Outstanding**

**Price-to-Book (P/B) = Stock Price / Book Value Per Share**

Book value measures the accounting value of equity. For asset-heavy businesses (banks, insurers, real estate), it is a meaningful valuation anchor. For asset-light businesses (software, brand), book value understates true value because intangible assets are not capitalized.

### Tangible Book Value (TBV)

**TBV = Total Equity − Goodwill − Intangible Assets**

More conservative than book value: strips out acquisition-created goodwill and intangibles that may be impaired. Especially relevant when analyzing financial institutions or potential distress situations.

**Tangible Book Value Per Share = TBV / Shares Outstanding**

### Net Debt

**Net Debt = Total Debt − Cash & Short-term Investments**

A company with $500M in debt but $600M in cash has net cash of $100M. Net debt is used in enterprise value calculations and to assess true leverage burden.

---

## Red Flags on the Balance Sheet

**1. Goodwill > 30–40% of total assets**
The balance sheet is largely supported by acquisition assumptions. One or two impairments can eviscerate book value.

**2. Accounts receivable growing faster than revenue**
Potential revenue recognition manipulation, deteriorating collections, or aggressive deal structuring to hit targets.

**3. Inventory growing faster than COGS**
Demand may be weakening. Risk of future write-downs that hit the income statement.

**4. Large off-balance-sheet obligations in footnotes**
Operating lease commitments, purchase obligations, or contingent liabilities that are economically real but absent from headline metrics.

**5. Equity declining due to buybacks at high prices**
Companies that buy back stock aggressively during bull markets often end up with negative book equity (technically bankrupt on paper) while having paid above intrinsic value. Examples: McDonald's, Boeing.

**6. Rising DTAs without clear path to income**
Deferred tax assets require future taxable income to be realized. If a struggling company has built up large DTAs, they may need to be written down (valuation allowance), hitting earnings.

**7. Debt maturity concentration**
If a large proportion of debt matures in 1–3 years during a period of high rates, the company faces significant refinancing risk. Check the debt maturity schedule in the footnotes.
