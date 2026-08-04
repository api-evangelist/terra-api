# Terra (terra-api)

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

Terra is a unified wearables and health-data API that aggregates data from 500+ wearables, fitness trackers, and health apps - Garmin, Fitbit, Oura, Apple Health, Whoop, Strava, Google Fit, Polar, Withings, and many more - behind a single normalized REST interface. Developers connect end users through the Terra Widget or a custom authentication flow, then receive normalized Activity, Body, Daily, Sleep, Nutrition, Menstruation, and Athlete data. Terra's primary delivery model is asynchronous: requested and newly available health data is streamed to a developer-configured webhook destination rather than returned inline, with REST read endpoints available for on-demand historical pulls. All requests use two headers, `dev-id` (public) and `x-api-key` (secret).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/terra-api/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/terra-api/refs/heads/main/apis.yml)

## Tags

- Wearables
- Health Data
- Fitness
- Aggregator
- Webhooks
- Digital Health

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Terra Authentication API

Connect end users to their wearable and health accounts. Generate a Terra Widget session or a custom authentication link, mint auth tokens for the Terra mobile SDKs, and deauthenticate users to revoke data access.

- **Human URL:** [https://docs.tryterra.co/health-and-fitness-api/user-authentication](https://docs.tryterra.co/health-and-fitness-api/user-authentication)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Authentication
- Widget
- User Onboarding

#### Properties

- [Documentation](https://docs.tryterra.co/health-and-fitness-api/user-authentication)
- [API Reference](https://docs.tryterra.co/reference/health-and-fitness-api/readme)
- [OpenAPI](openapi/terra-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/terra-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/terra-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Terra User Management API

Look up connected users and their metadata. Retrieve a single user by Terra user ID or your reference ID, list all connected user IDs (subscriptions) with pagination, and batch-query multiple users at once via bulk user info.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/readme](https://docs.tryterra.co/reference/health-and-fitness-api/readme)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Users
- Subscriptions
- Management

### Terra Activity API

Retrieve normalized workout and exercise sessions for a user over a date range - GPS routes, heart-rate zones, distance, calories, power, cadence, and per-activity samples. Streamed to your webhook when `to_webhook` is true.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/data-models](https://docs.tryterra.co/reference/health-and-fitness-api/data-models)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Activity
- Workouts
- Exercise

### Terra Body API

Retrieve body and biometric measurements for a user - weight, body composition, blood pressure, blood glucose, SpO2, hydration, temperature, and continuous heart-rate samples - normalized across every supported device.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/data-models](https://docs.tryterra.co/reference/health-and-fitness-api/data-models)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Body
- Biometrics
- Heart Rate

### Terra Daily API

Retrieve day-level aggregated summaries for a user - steps, distance, active and total calories, active durations, heart-rate summaries, and stress - rolled up per calendar day across supported wearables.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/data-models](https://docs.tryterra.co/reference/health-and-fitness-api/data-models)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Daily
- Steps
- Summaries

### Terra Sleep API

Retrieve sleep sessions for a user - total, light, deep, and REM durations, sleep stages, respiration, heart-rate variability, and readiness or recovery metrics - normalized across Oura, Whoop, Garmin, Fitbit, and others.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/data-models](https://docs.tryterra.co/reference/health-and-fitness-api/data-models)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Sleep
- Sleep Stages
- Recovery

### Terra Nutrition API

Retrieve logged nutrition and dietary intake for a user - meals, macronutrients, micronutrients, water intake, and per-meal detail - from apps such as MyFitnessPal and other supported nutrition sources.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/data-models](https://docs.tryterra.co/reference/health-and-fitness-api/data-models)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Nutrition
- Diet
- Macros

### Terra Menstruation API

Retrieve menstrual cycle and reproductive health data for a user - cycle phases, period days, predicted and actual menstruation events, and related symptoms - from cycle-tracking apps and wearables.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/data-models](https://docs.tryterra.co/reference/health-and-fitness-api/data-models)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Menstruation
- Cycle Tracking
- Womens Health

### Terra Athlete API

Retrieve the athlete profile for a connected user - name, age, sex, height, weight, country, and other demographic attributes reported by the upstream provider - to enrich and contextualize their health data.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/data-models](https://docs.tryterra.co/reference/health-and-fitness-api/data-models)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Athlete
- Profile
- Demographics

### Terra Integrations API

Discover which of Terra's 500+ wearables, trackers, and health apps are available to your account. List supported integrations, and query a detailed view filtered by the data scopes and SDKs each provider supports.

- **Human URL:** [https://docs.tryterra.co/reference/health-and-fitness-api/supported-integrations](https://docs.tryterra.co/reference/health-and-fitness-api/supported-integrations)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Integrations
- Providers
- Catalog

### Terra Webhooks

Terra's primary data-delivery mechanism. Rather than a polling or WebSocket transport, Terra streams normalized health data and lifecycle events - auth, deauth, connection errors, and activity/body/daily/sleep/nutrition/menstruation payloads - by HTTP POST to a developer-configured webhook endpoint, signed for verification. Historical data requests with `to_webhook=true` are fulfilled asynchronously to this same destination.

- **Human URL:** [https://docs.tryterra.co/health-and-fitness-api/integration-setup/setting-up-data-destinations/webhooks](https://docs.tryterra.co/health-and-fitness-api/integration-setup/setting-up-data-destinations/webhooks)
- **Base URL:** `https://api.tryterra.co/v2`

#### Tags

- Webhooks
- Data Streaming
- Events

## Common Properties

- [GitHub Organization](https://github.com/tryterra)
- [LinkedIn](https://www.linkedin.com/company/terraapi)
- [Website](https://tryterra.co)
- [Documentation](https://docs.tryterra.co)
- [Plans](plans/terra-api-plans-pricing.yml)
- [Rate Limits](rate-limits/terra-api-rate-limits.yml)
- [Fin Ops](finops/terra-api-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
