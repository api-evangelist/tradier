---
name: Stream real-time market data
description: Create a short-lived streaming session over REST, then subscribe to live quote/trade/timesale events over WebSocket.
api: openapi/tradier-openapi.yml
operations: [createMarketStreamingSession, createAccountStreamingSession]
generated: '2026-07-22'
method: generated
---

# Stream real-time market data

Streaming requires a **production** token (the `stream` OAuth scope for partner
apps); the sandbox does not stream real-time data.

1. **Create a session** with `createMarketStreamingSession`
   (`POST /markets/events/session`) — or `createAccountStreamingSession`
   (`POST /accounts/events/session`) for order/account events. The response
   contains a `sessionid`.
2. **Connect fast**: the sessionid is valid for at most **5 minutes** before
   connecting, and only **one streaming session per user** may be open.
3. **Open the WebSocket** to `wss://ws.tradier.com/v1/markets/events` (market)
   or `wss://ws.tradier.com/v1/accounts/events` (account).
4. **Send the subscription payload** as JSON referencing the sessionid, e.g.
   `{"symbols": ["AAPL","SPY"], "sessionid": "<sessionid>", "filter": ["quote","trade","timesale"]}`.
   Payload types: `quote`, `trade`, `summary`, `timesale`, `tradex`.
5. **Modify mid-stream** by sending a new payload with the same sessionid.

The full channel/message contract is captured in `asyncapi/tradier-asyncapi.yml`.

Rules:
- If the socket drops, mint a NEW session via REST — sessionids are single-use
  bootstrap credentials, not long-lived tokens.
- Prefer streaming over polling `getQuotes`; polling burns the 120 req/min
  market-data budget.
