# Megaphone (megaphone)

Megaphone (Megaphone by Spotify) is an enterprise podcast hosting, distribution, and advertising-monetization platform, owned by Spotify since its 2020 acquisition. Its REST API lets podcast producers and partners programmatically manage networks, podcasts, and episodes, run dynamic ad insertion, and operate direct-sales advertising - campaigns, orders, advertisements, advertisers, and targeting - plus pull metrics and impressions via export services.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/megaphone/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/megaphone/refs/heads/main/apis.yml)

## Access Model

Megaphone's API documentation is **publicly readable** - the developer portal ([developers.megaphone.fm](https://developers.megaphone.fm/)), an Apiary interactive reference, and a support-center API overview are all open. **Using** the API, however, requires a **paid Megaphone account**: an API token is generated for every account and viewed under User Settings. Megaphone is a paid enterprise platform (Professional plan from $99/month; Enterprise pricing is contact-sales), so the API is best described as **public-docs / account-gated** rather than fully self-serve or fully gated.

- **Base URL (v1):** `https://cms.megaphone.fm/api`
- **Base URL (v2 Direct Sales):** `https://cms.megaphone.fm/api/v2`
- **Auth:** header `Authorization: Token token="<API_TOKEN>"` (per-user, role-scoped; treat as a password, do not reuse across orgs)
- **Pagination:** RFC 5988 Link header (`rel="next"`) with `page` / `per_page`
- **Rate limit:** 60 requests/minute (1 request/second)

> The v1 network/podcast/episode/campaign/order/advertisement paths are confirmed from Megaphone's docs, the Apiary reference, and the open-source `theatlantic/megaphone` Python client. The **v2 Direct Sales** paths and the **Metrics/Impressions export** paths are honestly **modeled** from the documented resource lists where the exact reference was not publicly retrievable. The v2 Direct Sales endpoints became available April 15, 2026 and the legacy Direct Sales endpoints are scheduled to sunset July 14, 2026.

## Tags

- Podcasting
- Podcast Hosting
- Advertising
- Ad Monetization
- Dynamic Ad Insertion
- Media
- Spotify

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Megaphone Networks API

Read a network (the top-level account container) and list the podcasts that belong to it.

- **Human URL:** [https://developers.megaphone.fm/](https://developers.megaphone.fm/)
- **Base URL:** `https://cms.megaphone.fm/api`

### Megaphone Podcasts API

Create, list, retrieve, update, and delete podcasts within a network, including title, artwork, categories, distribution settings, and monetization configuration.

- **Human URL:** [https://developers.megaphone.fm/](https://developers.megaphone.fm/)
- **Base URL:** `https://cms.megaphone.fm/api`

### Megaphone Episodes API

Manage episodes under a podcast - create, list, retrieve, update, delete, upload audio, set publish dates and draft state, and configure ad-insertion points for dynamic ad insertion.

- **Human URL:** [https://developers.megaphone.fm/](https://developers.megaphone.fm/)
- **Base URL:** `https://cms.megaphone.fm/api`

### Megaphone Campaigns and Orders API

Direct-sales advertising surface (v1) scoped to an organization - campaigns, campaign orders and promo orders, and the advertisements attached to each order. Legacy; superseded by v2.

- **Human URL:** [https://developers.megaphone.fm/](https://developers.megaphone.fm/)
- **Base URL:** `https://cms.megaphone.fm/api`

### Megaphone Direct Sales API v2

Enhanced REST API (v2) for direct-sales advertising - advertisers, campaigns, orders, assets, advertisements, and targeting. Effective April 15, 2026. Some v2 path details are modeled.

- **Human URL:** [https://developers.megaphone.fm/](https://developers.megaphone.fm/)
- **Base URL:** `https://cms.megaphone.fm/api/v2`

### Megaphone Metrics and Impressions Export API

Bulk export surfaces - the Metrics Export Service and Impressions Export Service - for pulling download, listener, and ad-impression data. Endpoint shapes are modeled.

- **Human URL:** [https://developers.megaphone.fm/](https://developers.megaphone.fm/)
- **Base URL:** `https://cms.megaphone.fm/api`

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/megaphonepods)
- [Website](https://megaphone.spotify.com/)
- [Documentation](https://developers.megaphone.fm/)
- [API Reference](https://jsapi.apiary.io/apis/megaphoneapi/reference/podcasts.html)
- [Plans](plans/megaphone-plans-pricing.yml)
- [Rate Limits](rate-limits/megaphone-rate-limits.yml)
- [Fin Ops](finops/megaphone-finops.yml)
- [Pricing](https://megaphone.spotify.com/pricing)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
