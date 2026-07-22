---
name: Look up quotes and option chains
description: Fetch live quotes for symbols, then walk expirations and strikes to pull a full option chain with Greeks.
api: openapi/tradier-openapi.yml
operations: [getClock, getQuotes, getOptionExpirations, getOptionStrikes, getOptionChains]
generated: '2026-07-22'
method: generated
---

# Look up quotes and option chains

Authenticate every call with `Authorization: Bearer <token>` and `Accept: application/json`
(XML is the default and is being deprecated — always send the JSON Accept header).

1. **Check the market state** with `getClock` (`GET /markets/clock`) if freshness
   matters — quotes outside market hours are stale by definition.
2. **Get quotes** with `getQuotes` (`GET /markets/quotes?symbols=AAPL,SPY`).
   Symbols are comma-separated; option symbols use OCC format.
3. **Find expirations** for an underlying with `getOptionExpirations`
   (`GET /markets/options/expirations?symbol=AAPL`).
4. **Optionally list strikes** for one expiration with `getOptionStrikes`
   (`GET /markets/options/strikes?symbol=AAPL&expiration=...`).
5. **Pull the chain** with `getOptionChains`
   (`GET /markets/options/chains?symbol=AAPL&expiration=...&greeks=true`) —
   `greeks=true` adds delta/gamma/theta/vega columns.

Rules:
- Market-data calls share a 120 req/min production budget (60 in sandbox); watch
  the `X-Ratelimit-Available` response header and back off before it hits zero
  (see `rate-limits/tradier-rate-limits.yml`).
- JSON responses are XML-translated: a list with a single element may present as
  an object, not an array — normalize both shapes.
- For continuous prices, do not poll: use the streaming skill instead.
