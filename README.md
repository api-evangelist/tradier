# Tradier (tradier)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
