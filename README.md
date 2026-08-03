# Adafruit IO (adafruit-io)

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

Adafruit IO is a cloud Internet of Things platform from Adafruit Industries built for makers, hobbyists, students, and STEM educators. It provides feed-based time-series storage, drag-and-drop dashboards with 20+ visualization block types, actions/triggers for SMS/voice/email/webhook notifications, built-in services (time, weather, randomizer, air quality), and a complete REST + MQTT API surface for Adafruit Feather and Metro boards, ESP32 / ESP8266 / Pico microcontrollers, Raspberry Pi, and any other HTTP- or MQTT-capable hardware. First-class Arduino, CircuitPython, and Python client libraries plus the no-code Wippersnapper firmware make it the easiest way for hobbyists to get their projects onto the Internet of Things.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/adafruit-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/adafruit-io/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- IoT
- Internet of Things
- MQTT
- Maker
- Hobbyist
- CircuitPython
- Arduino
- ESP32
- Feather
- Dashboards
- Time Series

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Adafruit IO REST API

REST API for Adafruit IO providing CRUD operations across feeds, time-series data points, groups, dashboards, dashboard blocks, triggers (reactive and scheduled actions), API tokens, permissions/ACL, account activities, and inbound webhooks. Base URL https://io.adafruit.com/api/v2 — authenticated via the X-AIO-Key header or query parameter using an Adafruit IO API key. Supports batch data writes, chart-aggregated reads, positional queries (first/last/previous/next/retain), and Link-header pagination up to 1000 records per page.

- **Human URL:** [https://io.adafruit.com/api/docs/](https://io.adafruit.com/api/docs/)
- **Base URL:** `https://io.adafruit.com/api/v2`

#### Tags

- IoT
- Internet of Things
- Feeds
- Data
- Dashboards
- Maker

#### Properties

- [Documentation](https://io.adafruit.com/api/docs/)
- [Documentation](https://io.adafruit.com/api/docs/#adafruit-io-http-api)
- [OpenAPI](openapi/adafruit-io-rest-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/adafruit-io-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adafruit-io-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/adafruit-io-feed-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/adafruit-io-data-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/adafruit-io-dashboard-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/adafruit-io-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Adafruit IO MQTT API

MQTT broker at io.adafruit.com for publish/subscribe access to Adafruit IO feeds and groups. TLS on port 8883, plaintext on 1883, and MQTT-over-WebSocket on port 443. Authenticate with your Adafruit IO username and API key. Supports QoS 0 and QoS 1 (QoS 2 not supported); MQTT retain flag is not honored — use the /get topic modifier to fetch the last value of a feed instead. Topic structure includes feed topics ({username}/feeds/{key}), compact aliases ({username}/f/{key}), JSON/CSV suffixes, group topics ({username}/groups/{key}), throttle ({username}/throttle), and errors ({username}/errors). Wildcard subscriptions with `+` and `#` are supported for feed discovery.

- **Human URL:** [https://io.adafruit.com/api/docs/mqtt.html](https://io.adafruit.com/api/docs/mqtt.html)
- **Base URL:** `mqtts://io.adafruit.com:8883`

#### Tags

- IoT
- Internet of Things
- MQTT
- Realtime
- Feeds

#### Properties

- [Documentation](https://io.adafruit.com/api/docs/mqtt.html)
- [Documentation](https://io.adafruit.com/api/docs/mqtt.html#mqtt-topics)
- [Postman Collection](collections/adafruit-io-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adafruit-io-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adafruit IO Webhooks API

Token-authenticated inbound webhook endpoints that allow third-party services (IFTTT, Zapier, Make, or any HTTP client) to push data into an Adafruit IO feed without an API key. Endpoints include the standard JSON webhook (POST /webhooks/feed/:token), the raw-payload webhook (POST /webhooks/feed/:token/raw) for arbitrary request bodies, and a notify webhook (POST /webhooks/feed/:token/notify) for ping-style triggers. Tokens are generated per-feed and managed in the Adafruit IO UI.

- **Human URL:** [https://io.adafruit.com/api/docs/#webhooks](https://io.adafruit.com/api/docs/#webhooks)
- **Base URL:** `https://io.adafruit.com/api/v2/webhooks`

#### Tags

- IoT
- Internet of Things
- Webhooks
- Feeds

#### Properties

- [Documentation](https://io.adafruit.com/api/docs/#webhooks)
- [OpenAPI](openapi/adafruit-io-rest-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/adafruit-io-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adafruit-io-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Portal](https://io.adafruit.com)
- [Documentation](https://io.adafruit.com/api/docs/)
- [Documentation](https://io.adafruit.com/api/docs/cookbook.html)
- [Documentation](https://io.adafruit.com/api/docs/mqtt.html)
- [Getting Started](https://learn.adafruit.com/series/adafruit-io-basics)
- [Getting Started](https://learn.adafruit.com/welcome-to-adafruit-io)
- [Blog](https://io.adafruit.com/blog)
- [Changelog](https://io.adafruit.com/blog/changelog/)
- [Forum](https://forums.adafruit.com/viewforum.php?f=56)
- [Forum](https://discord.gg/adafruit)
- [Sign Up](https://io.adafruit.com/signup)
- [Login](https://io.adafruit.com/login)
- [Documentation](https://www.adafruit.com/iot)
- [Pricing](https://io.adafruit.com/plus)
- [Rate Limits](https://io.adafruit.com/api/docs/#rate-limiting)
- [Errors](https://io.adafruit.com/api/docs/#errors)
- [Authentication](https://io.adafruit.com/api/docs/#authentication)
- [Privacy Policy](https://www.adafruit.com/privacy)
- [Terms of Service](https://www.adafruit.com/termsofservice)
- [GitHub Organization](https://github.com/adafruit)
- [Source Code](https://github.com/adafruit/io-api)
- [SDK](https://github.com/adafruit/Adafruit_IO_Python)
- [SDK](https://github.com/adafruit/Adafruit_IO_Arduino)
- [SDK](https://github.com/adafruit/Adafruit_CircuitPython_AdafruitIO)
- [SDK](https://github.com/adafruit/io-client-ruby)
- [SDK](https://github.com/adafruit/adafruit-io-node)
- [SDK](https://github.com/adafruit/io-client-go)
- [Tool](https://github.com/adafruit/Adafruit_MQTT_Library)
- [Code Examples](https://github.com/adafruit/adafruit-io-basics)
- [Tool](https://github.com/adafruit/io-swagger-templates)
- [Tool](https://github.com/adafruit/adafruit-io-node-tunnel)
- [Documentation](https://www.adafruit.com/category/1011)
- [Documentation](https://www.adafruit.com/category/943)
- [Documentation](https://learn.adafruit.com/welcome-to-circuitpython)
- [Integrations](https://ifttt.com/adafruit)
- [Integrations](https://zapier.com/apps/adafruit-io/integrations)
- [Plans](https://io.adafruit.com/plus)
- [Plans](plans/adafruit-io-plans-pricing.yml)
- [Rate Limits](rate-limits/adafruit-io-rate-limits.yml)
- [Fin Ops](finops/adafruit-io-finops.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
