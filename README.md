# Megaphone (megaphone)

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
