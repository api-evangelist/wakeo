# Wakeo (wakeo)

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
