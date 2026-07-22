---
name: Place and track an equity order
description: Check buying power, place an equity order, then poll its status — including the HTTP-200 order-level error pattern — and cancel if needed.
api: openapi/tradier-openapi.yml
operations: [getUserProfile, getAccountBalances, placeOrder, getOrder, cancelOrder]
generated: '2026-07-22'
method: generated
---

# Place and track an equity order

Use the **sandbox** (`https://sandbox.tradier.com/v1`, sandbox token, paper
trading) until the flow is proven; the surface is identical to production
(`https://api.tradier.com/v1`). See `sandbox/tradier-sandbox.yml`.

1. **Resolve the account** with `getUserProfile` (`GET /user/profile`) — it
   returns the `account_id` values the other calls need.
2. **Check buying power** with `getAccountBalances`
   (`GET /accounts/{account_id}/balances`).
3. **Place the order** with `placeOrder` (`POST /accounts/{account_id}/orders`,
   body `application/x-www-form-urlencoded`): `class=equity`, `symbol`,
   `side=buy|sell`, `quantity`, `type=market|limit|stop|stop_limit`,
   `duration=day|gtc|pre|post`, plus `price`/`stop` when the type requires them.
4. **Poll status** with `getOrder` (`GET /accounts/{account_id}/orders/{order_id}`).
   CRITICAL: downstream rejections (risk management, market centers) still return
   **HTTP 200** from placeOrder — the rejection only appears in the order's
   `errors` property. Map codes with `errors/tradier-error-codes.yml`
   (e.g. `InitialMargin` = insufficient buying power, `MarketOrderIsGtc` =
   market orders must be day orders).
5. **Cancel if needed** with `cancelOrder`
   (`DELETE /accounts/{account_id}/orders/{order_id}`).

Rules:
- There is NO idempotency key (`conventions/tradier-conventions.yml`): on a
  timeout, list open orders with `listOrders` before retrying to avoid a
  duplicate order.
- Trading calls are limited to 60 req/min; standard account calls to 120 req/min
  in production.
- Market orders cannot be GTC; short-sale and margin restrictions surface as
  coded order errors, not HTTP failures.
