# Income and Neutral Strategies

Income strategies generate cash flow by selling option premium. They profit when the underlying stays within a range, when time passes (theta), and when implied volatility falls. They are best deployed in high-IV environments (IVR > 50%).

---

## Covered Call

### Setup

Own 100 shares of stock. Sell an OTM (or ATM) call against that stock position.

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral to slightly bullish |
| Capital | Full stock ownership |
| Income | Premium received from sold call |
| Max reward | Strike − purchase price + premium |
| Max risk | Stock falls to zero minus premium received |
| Breakeven | Stock purchase price − premium received |
| Assignment risk | If stock closes above strike at expiry, shares are called away |

### Payoff Example

Buy AAPL at $170. Sell 175 Call for $2.00 (30 DTE):
- Max profit: (175 − 170) + 2.00 = $7.00/share ($700)
- If AAPL closes at $165 at expiry: keep premium, stock position at $165 (better than no CC by $2)
- Breakeven: $168.00

### Income Enhancement

Annualized yield from covered calls: (Premium / Stock Price) × (365 / DTE) × 100%
- Example: $2.00 premium on $170 stock, 30 DTE → ($2/$170) × (365/30) = ~14.3% annualized yield

### Managing Covered Calls

- **Close early at 50% profit** (buy back call when it falls to $1.00 in the example above) — then sell the next one
- **Roll when challenged:** If stock approaches the strike, roll the call up and out (higher strike, farther DTE) for a credit or small debit
- **Assignment is OK if planned:** If shares get called away at the strike, you sell at a predetermined profit. The only problem is if the stock surges well above the strike — then you've capped your upside.
- **Don't sell calls on positions you want to hold:** Covered calls sacrifice upside. Only sell them on positions you'd be happy selling at the strike price.

---

## Cash-Secured Put (CSP)

### Setup

Sell an OTM put while holding cash equal to the obligation (strike × 100).

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral to bullish |
| Capital | Cash to buy 100 shares at strike if assigned |
| Income | Premium received |
| Max reward | Premium received |
| Max risk | Strike − premium (stock goes to zero) |
| Breakeven | Strike − premium |
| Assignment | If stock below strike at expiry, you buy shares at the strike price |

### Payoff Example

Stock at $50. Sell 47 Put for $1.00 (30 DTE). Hold $4,700 cash.
- Max profit: $100 per contract
- If assigned at 47, effective cost basis = $47 − $1.00 = $46.00/share
- Breakeven: $46.00

### CSP as a Stock Acquisition Strategy

CSPs are a way to set a limit order with a yield while waiting for a pullback:
- You want to own the stock at $46, it's currently at $50
- Sell the 47 put for $1 → either you're not assigned and keep $100, or you buy at an effective $46
- Repeat every month to reduce cost basis further

### Wheel Strategy

Combine covered calls and CSPs:
1. Sell CSP → if not assigned, repeat
2. If assigned (buy stock), sell covered call at or above cost basis
3. If called away (sell stock), return to step 1

The wheel generates continuous income but requires full capital commitment and carries full stock downside risk.

---

## Credit Spreads

Credit spreads are defined-risk versions of short puts and short calls. They limit both your maximum profit and maximum loss.

### Bull Put Spread

Sell a higher-strike put, buy a lower-strike put (same expiration).

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral to bullish (want stock above short put strike) |
| Credit received | Short put premium − long put premium |
| Max reward | Credit received |
| Max risk | Spread width − credit received |
| Breakeven | Short put strike − credit received |

**Example:** Stock at $100. Sell 95 Put at $2.50, Buy 90 Put at $0.80.
- Credit: $1.70 ($170/contract)
- Max loss: (95 − 90) − 1.70 = $3.30 ($330)
- Breakeven: $93.30

### Bear Call Spread

Sell a lower-strike call, buy a higher-strike call (same expiration).

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral to bearish (want stock below short call strike) |
| Credit received | Short call premium − long call premium |
| Max reward | Credit received |
| Max risk | Spread width − credit received |
| Breakeven | Short call strike + credit received |

**Example:** Stock at $100. Sell 105 Call at $2.00, Buy 110 Call at $0.60.
- Credit: $1.40 ($140/contract)
- Max loss: (110 − 105) − 1.40 = $3.60 ($360)
- Breakeven: $106.40

### Credit Spread Strike Selection

- **Short strike delta:** 25–35Δ for a balance of premium and probability of success
- **Spread width:** $5–$10 wide for liquid underlyings; wider spreads reduce gamma but also reduce ROC
- **Target premium:** Collect at least 30–40% of spread width; otherwise the risk/reward is too poor
- Return on capital = credit / max risk. Example: $1.70 credit on $3.30 max risk = 51.5% ROC potential

---

## Iron Condor

### Setup

Combine a bull put spread and a bear call spread on the same underlying and expiration.

```
        Long Put ─── Short Put ─── Stock Range ─── Short Call ─── Long Call
           |             |                              |              |
           ▼             ▼                              ▼              ▼
       (protection)  (income)                       (income)     (protection)
```

| Parameter | Detail |
|-----------|--------|
| Bias | Neutral; want stock to stay within a range |
| Credit | Bull put spread credit + bear call spread credit |
| Max reward | Total credit received |
| Max risk | Wider spread width − total credit |
| Profit range | Short put strike to short call strike |

### Payoff Example

Stock at $100. Sell 90/85 put spread for $1.20 credit. Sell 110/115 call spread for $0.90 credit.
- Total credit: $2.10 ($210/contract)
- Max loss: $5.00 − $2.10 = $2.90 ($290) on either side
- Profit range: $90 to $110 at expiry
- Probability of full profit: ~40–50% (depending on strikes chosen)

### Iron Condor Management

- **Entry timing:** 30–45 DTE for optimal theta decay; close at 21 DTE to avoid gamma risk
- **Profit target:** Close at 50% of max profit. On $2.10 credit, buy back at $1.05.
- **Adjustment when tested:** If stock approaches one side, either close that spread at a loss, or roll it out and further OTM for a credit
- **Do not hold to expiry:** In the final week, gamma risk spikes and a single bad day can wipe out weeks of gains

---

## Iron Butterfly

### Setup

Sell ATM straddle, buy OTM call and put wings for protection.

```
        Long Put ─── Short Put = Short Call ─── Long Call
            |               ATM                     |
```

| Parameter vs Iron Condor | Iron Butterfly |
|--------------------------|----------------|
| Short strikes | Both at ATM (same strike) |
| Maximum credit | Higher (ATM options have most extrinsic) |
| Profit range | Narrower (only around ATM) |
| Probability of profit | Lower than condor |
| Risk/reward | Better ratio |

**When to use:** When you expect the underlying to pin very close to current price (e.g., after a catalyst has resolved, stock likely to range-trade). Expiration week often sees high iron butterfly success on indices.

---

## Selecting Strikes, DTE, and When to Manage

### Standard Income Trade Parameters

| Parameter | Typical Choice | Reason |
|-----------|---------------|--------|
| **DTE at entry** | 30–45 days | Captures fastest portion of theta decay curve |
| **Short strike delta** | 25–30Δ | Balance of premium and ~70% probability of success |
| **Spread width** | $5–$10 | Defines max loss; wider = more premium but more risk |
| **Credit target** | ≥30% of spread width | Below this, risk/reward is too poor |
| **Profit target** | 50% of max credit | Highest risk-adjusted return; close early |
| **Loss limit** | 2× credit received | Close the spread to prevent full loss |
| **DTE to manage** | 21 DTE | Gamma spikes here; avoid holding through final week |

### IV Environment

- IVR > 50%: ideal entry; premium is elevated
- IVR 30–50%: acceptable; use tighter spreads to reduce exposure
- IVR < 30%: avoid selling premium; the credit barely compensates for risk
