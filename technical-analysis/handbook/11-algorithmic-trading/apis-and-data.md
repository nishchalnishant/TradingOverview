# APIs for Trading and Data Sources

## Broker APIs

- **Purpose:** Send **orders** (market, limit, stop), **cancel** orders, and often **stream** quotes and positions. Used for **automated execution** and sometimes for **data** (e.g. last price, order book).
- **Examples:** Interactive Brokers (TWS API, IBKR API), Alpaca, TD Ameritrade, OANDA (forex), Binance (crypto). Most are **REST** and/or **WebSocket** (for real-time).
- **Security:** Use **API keys** or OAuth; **never** commit keys to public repos. Use environment variables or a secure config. Prefer **paper** or **sandbox** first.
- **Rate limits:** Brokers limit requests per second/minute. Your code must respect limits and handle **retries** and **errors** (e.g. network failure, reject).

---

## Data APIs

- **Purpose:** **Historical** OHLCV and **real-time** quotes for backtesting and signals. Separate from execution (you can use one provider for data and another for execution).
- **Free/low-cost:** Yahoo Finance (yfinance), Alpha Vantage, FRED (macro). **Paid:** Polygon, Quandl, Bloomberg, Refinitiv. **Crypto:** Binance, CoinGecko, etc.
- **Considerations:** **Adjustments** (splits, dividends) for equities; **quality** and **latency** for live; **history length** (some only offer 1–2 years for free).

---

## Basic Python Usage

- **REST:** Use **requests** or **httpx** to call API endpoints (e.g. GET /bars, POST /order). Parse JSON response.
- **WebSocket:** Use **websocket-client** or **asyncio** for streaming (e.g. live quotes). Handle reconnects.
- **Libraries:** Many brokers have **official** or **community** Python wrappers (e.g. **ib_insync** for IB, **alpaca-trade-api** for Alpaca). They abstract HTTP/WebSocket and often provide convenience methods (e.g. place_order, get_bars).

---

## Risk Management

- **Paper first:** Always test **paper** or **small size** before full automation. API bugs (e.g. wrong side, wrong size) can be costly.
- **Kill switch:** Have a way to **disable** the algo or **close all** positions quickly (e.g. button in UI, or script that flattens positions). Use **max position size** and **max daily loss** in code.

---

*See also: [Backtesting Frameworks and Stack](backtesting-frameworks-and-stack.md) | [10 — Tools: Python and TradingView](../10-backtesting/tools-python-tradingview.md)*
