# Option Pricing

## Why Pricing Models Matter

Options do not have a single "correct" price — they have a **theoretical value** derived from a model and a **market price** driven by supply, demand, and the implied volatility baked in by market participants. Understanding pricing models lets you:
- Identify when options are cheap or expensive relative to historical norms
- Compute the Greeks (sensitivities) your broker displays
- Understand which inputs drive price so you know what to hedge

---

## Black-Scholes Model

The Black-Scholes-Merton (BSM) model is the foundation of modern option pricing. It gives a closed-form formula for European-style options. The model assumes:
- Continuous trading, no dividends (in the basic form)
- Constant volatility and risk-free rate through expiration
- Log-normally distributed returns

### Five Inputs

| Input | Symbol | Effect on Call Price | Effect on Put Price |
|-------|--------|---------------------|---------------------|
| **Underlying price** | S | Increases | Decreases |
| **Strike price** | K | Decreases | Increases |
| **Time to expiration** | T (years) | Increases | Increases |
| **Risk-free interest rate** | r | Increases (slightly) | Decreases (slightly) |
| **Implied volatility** | σ | Increases | Increases |

Volatility is the only input that cannot be directly observed — all others are known. This is why **implied volatility (IV)** is the most debated and traded input.

### BSM Call Formula (conceptual)

```
C = S × N(d1) − K × e^(−rT) × N(d2)

where:
  d1 = [ln(S/K) + (r + σ²/2)T] / (σ√T)
  d2 = d1 − σ√T
  N(x) = cumulative standard normal distribution
```

- N(d2) is approximately the risk-neutral probability the option expires ITM
- N(d1) is the option's delta
- The formula decomposes into: (value of receiving the stock if exercised) − (present value of paying the strike)

### BSM Put Formula

```
P = K × e^(−rT) × N(−d2) − S × N(−d1)
```

### BSM Limitations

- Assumes **constant volatility**: real markets exhibit volatility smile/skew (see Section 3)
- Assumes **log-normal returns**: actual returns have fat tails (crash risk is underpriced by BSM)
- No early exercise: only valid for European options
- No jumps: gaps (earnings, events) violate the continuous-price assumption

Despite these limitations, BSM remains the industry standard for quoting options (via implied volatility) and computing Greeks.

---

## Binomial Model

The binomial model prices options by building a discrete tree of possible price paths. At each time step, the stock can move **up** by factor u or **down** by factor d.

```
         S·u·u
        /
      S·u
     /   \
    S     S·u·d
     \   /
      S·d
        \
         S·d·d
```

At expiration (the terminal nodes), calculate the option payoff. Then discount backwards through the tree using risk-neutral probabilities to find today's value.

**Why it matters:**
- Handles **American-style early exercise** correctly (check at each node whether exercising early is worth more than holding)
- Intuitive: shows that option value is about probability-weighted future payoffs discounted back
- Converges to Black-Scholes as the number of steps → ∞

---

## What Drives Option Prices

### Moneyness

The single biggest driver of premium level. Deep OTM options are cheap; deep ITM options are expensive in dollar terms but have low time value.

| Moneyness | Delta approx | Time Value | Intrinsic Value |
|-----------|-------------|------------|-----------------|
| Deep OTM | 0.05–0.15 | Low | Zero |
| OTM | 0.15–0.40 | Moderate | Zero |
| ATM | ~0.50 | Maximum | Zero (approx) |
| ITM | 0.60–0.85 | Moderate | Yes |
| Deep ITM | 0.85–1.00 | Very low | Most of premium |

Time value peaks at-the-money because ATM options have the highest uncertainty about whether they will expire ITM or OTM.

### Time to Expiration

Time value decays as expiration approaches, and the decay accelerates. The rate of decay is theta (Section 2).

```
Time value remaining (approximate):
  90 DTE → 100% of time value
  45 DTE → ~71% of time value
  21 DTE → ~48%
   7 DTE → ~28%
   1 DTE → ~10%
```

(Based on square root of time relationship: √(t/T))

### Implied Volatility

IV is the market's consensus expectation of future realized volatility, expressed as an annualized standard deviation. If a stock has IV of 30%, the market implies a one-standard-deviation annual move of 30%.

- **Daily expected move** ≈ Stock Price × IV / √252
- **Weekly expected move** ≈ Stock Price × IV / √52
- **Monthly expected move** ≈ Stock Price × IV / √12

Higher IV inflates all options (calls and puts). When IV rises, long options gain value; when IV falls (IV crush), long options lose value even if the stock moves in the right direction.

---

## Theoretical Value vs Market Price

| Concept | Description |
|---------|-------------|
| **Theoretical value** | Price output from BSM given your inputs including an assumed volatility |
| **Market price** | Actual price on the exchange; reflects supply/demand |
| **Implied volatility** | The volatility you must plug into BSM to match the market price |

When you buy an option at market price and convert that to implied volatility, you are effectively paying for that level of expected future volatility. If actual realized volatility ends up lower than IV, the seller wins on average.

**Overpriced vs underpriced:**
- IV > expected future realized vol → option is expensive → sellers have edge
- IV < expected future realized vol → option is cheap → buyers have edge

This comparison drives the volatility strategies in Section 3.

---

## Put-Call Parity

Put-call parity is a no-arbitrage relationship between European call and put prices on the same underlying, strike, and expiration:

```
C − P = S − K × e^(−rT)

Rearranged:
C + K × e^(−rT) = P + S
(call + PV of strike = put + stock)
```

**Interpretation:** Owning a call and lending the PV of the strike is equivalent to owning a put and the stock. If this relationship breaks, there is a riskless arbitrage.

### Practical Uses

1. **Synthetic positions:** You can synthesize any position using the others.
   - Synthetic long stock = long call + short put (same strike/expiry)
   - Synthetic long call = long put + long stock
   - Synthetic long put = long call + short stock

2. **Pricing check:** If puts are quoted significantly more than put-call parity implies, there may be a dividend or borrow cost affecting the relationship.

3. **Risk reversal pricing:** The relationship explains why risk reversals (selling a put, buying a call) are a common way to take a synthetic long position with no net premium.

### Put-Call Parity with American Options

The strict equality breaks for American options because early exercise is possible. The relationship becomes an **inequality**:

```
S − K ≤ C − P ≤ S − K × e^(−rT)
```

The spread between the two bounds reflects the value of early exercise flexibility.
