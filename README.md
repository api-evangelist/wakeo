# Wakeo (wakeo)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Wakeo is a Paris-based SaaS platform for real-time multimodal supply-chain visibility across sea, air, road, rail, and parcel. It combines carrier, telematics, and AIS tracking data with data-science predictions to deliver predictive door-to-door ETAs, milestone events, congestion and disruption alerts, carbon-footprint reporting, and route reliability scoring. Wakeo's REST API and webhooks let customers pull transport orders and push enriched ETAs and tracking updates into a TMS, ERP, or MRP.

## Access Model (read first)

**Wakeo is an enterprise, customer-provisioned API.** It is not a self-serve, sign-up-and-go developer platform:

- The API reference lives at [https://docs.wakeo.co/docs/getting-started](https://docs.wakeo.co/docs/getting-started) **behind a password wall** (confirmed 2026-07-12: the host 302-redirects to `/password`). Access is granted by a Wakeo Customer Success representative or by emailing **support@wakeo.co**.
- The production API host **`https://api.wakeo.co` is confirmed live** and fronted by **AWS API Gateway** - unauthenticated requests return `HTTP 403 ForbiddenException`.
- Authentication is **OAuth 2.0** - every request carries `Authorization: Bearer <ACCESS_TOKEN>` (per Wakeo's published documentation).
- There is **no public pricing**; commercial terms are enterprise / contact-sales.

### Confirmed vs. modeled

| Aspect | Status |
| --- | --- |
| Base host `https://api.wakeo.co` (AWS API Gateway) | **Confirmed** (live probe) |
| OAuth 2.0 Bearer authentication | **Confirmed** (published docs) |
| REST + webhooks; no WebSocket | **Confirmed** (no `wss://` documented) |
| Exact resource paths, version prefix, query params | **Modeled** (reference is password-walled) |
| Request/response schemas | **Modeled** |

The OpenAPI in this repo is an **honest model** reconstructed from Wakeo's public capability descriptions (shipment tracking, ETA, positions, events, webhooks). Every modeled path is flagged with `x-wakeo-modeled: true`. Reconcile against the private reference before use.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/wakeo/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/wakeo/refs/heads/main/apis.yml)

## Tags

- Supply Chain
- Transportation Visibility
- Real-Time Visibility
- Multimodal
- Logistics
- Shipment Tracking
- ETA
- Freight
- Supply Chain Visibility
- SaaS

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### Wakeo Shipments API

Register and manage tracked shipments / transport orders across sea, air, road, rail, and parcel, and pull the latest transport orders into Wakeo.

- **Human URL:** [https://docs.wakeo.co/docs/getting-started](https://docs.wakeo.co/docs/getting-started)
- **Base URL:** `https://api.wakeo.co`

#### Tags

- Shipments
- Transport Orders
- Multimodal

#### Properties

- [Documentation](https://docs.wakeo.co/docs/getting-started)
- [OpenAPI](openapi/wakeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/wakeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/wakeo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Wakeo Tracking API

Retrieve predictive door-to-door ETAs, geolocation positions, and milestone events (departures, arrivals, port calls, transshipments, PODs, congestion and disruption alerts) for a tracked shipment.

- **Human URL:** [https://docs.wakeo.co/docs/getting-started](https://docs.wakeo.co/docs/getting-started)
- **Base URL:** `https://api.wakeo.co`

#### Tags

- Tracking
- ETA
- Real-Time Visibility

#### Properties

- [Documentation](https://docs.wakeo.co/docs/getting-started)
- [OpenAPI](openapi/wakeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/wakeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/wakeo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Wakeo Webhooks API

Subscribe customer endpoints to shipment tracking and ETA update events so Wakeo can push enriched data into a TMS, ERP, or MRP. Server-to-endpoint HTTPS webhooks, not WebSocket.

- **Human URL:** [https://docs.wakeo.co/docs/getting-started](https://docs.wakeo.co/docs/getting-started)
- **Base URL:** `https://api.wakeo.co`

#### Tags

- Webhooks
- Push Notifications
- Integration

#### Properties

- [Documentation](https://docs.wakeo.co/docs/getting-started)
- [OpenAPI](openapi/wakeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/wakeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/wakeo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Domain Security](security/wakeo-domain-security.yml)
- [Authentication](authentication/wakeo-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/wakeo)
- [Website](https://wakeo.co)
- [Documentation](https://docs.wakeo.co/docs/getting-started)
- [Plans](plans/wakeo-plans-pricing.yml)
- [Rate Limits](rate-limits/wakeo-rate-limits.yml)
- [Fin Ops](finops/wakeo-finops.yml)
- [Blog](https://wakeo.co/blog/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
