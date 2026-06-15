# Tradier (tradier)

Tradier is a brokerage platform offering REST and WebSocket APIs for trading US equities, options, and futures, plus market data and account-opening services. The Tradier Brokerage API exposes account, trading, market data, fundamentals, watchlist, and streaming endpoints under a single base URL.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/tradier/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/tradier/refs/heads/main/apis.yml)

## Tags

- Fintech
- Trading
- Stocks
- Options
- Brokerage
- Streaming

## Timestamps

- **Created:** 2026-05-08
- **Modified:** 2026-05-08

## APIs

### Tradier Brokerage API

The Tradier Brokerage API provides REST endpoints for placing equity, option, and multileg orders, retrieving account balances, positions, orders, and history, and accessing market data including quotes, option chains, time and sales, fundamentals, and corporate calendars. A sandbox base URL is available at api.sandbox.tradier.com/v1.

- **Human URL:** [https://docs.tradier.com/](https://docs.tradier.com/)
- **Base URL:** `https://api.tradier.com/v1`

#### Tags

- Trading
- Stocks
- Options
- Account
- Orders
- Market Data

#### Properties

- [Documentation](https://docs.tradier.com/)
- [Sandbox](https://api.sandbox.tradier.com/v1)

### Tradier Streaming API

The Tradier Streaming API delivers real-time market and account events over HTTP and WebSocket. Quote, trade, summary, timesale, and order events are streamed; client first creates a session via the brokerage REST endpoints and connects to stream.tradier.com.

- **Human URL:** [https://docs.tradier.com/brokerage-api/streaming](https://docs.tradier.com/brokerage-api/streaming)
- **Base URL:** `https://stream.tradier.com/v1`

#### Tags

- Streaming
- WebSocket
- HTTP
- Real-time
- Market Data

#### Properties

- [Documentation](https://docs.tradier.com/brokerage-api/streaming)
- [AsyncAPI](asyncapi/tradier-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)

## Common Properties

- [GitHub Organization](https://github.com/tradier)
- [LinkedIn](https://www.linkedin.com/company/tradier)
- [Portal](https://tradier.com/)
- [Documentation](https://docs.tradier.com/)
- [Pricing](https://tradier.com/individuals/pricing)
- [Status Page](https://status.tradier.com/)
- [Plans](plans/tradier-plans-pricing.yml)
- [Rate Limits](rate-limits/tradier-rate-limits.yml)
- [Fin Ops](finops/tradier-finops.yml)
- [L L Ms Txt](https://docs.tradier.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
