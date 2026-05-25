# Adafruit IO (adafruit-io)
Adafruit IO is a cloud Internet of Things platform from Adafruit Industries built for makers, hobbyists, students, and STEM educators. It provides feed-based time-series storage, drag-and-drop dashboards with 20+ visualization block types, actions/triggers for SMS/voice/email/webhook notifications, built-in services (time, weather, randomizer, air quality), and a complete REST + MQTT API surface for Adafruit Feather and Metro boards, ESP32 / ESP8266 / Pico microcontrollers, Raspberry Pi, and any other HTTP- or MQTT-capable hardware.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/adafruit-io/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - IoT, Internet of Things, MQTT, Maker, Hobbyist, CircuitPython, Arduino, ESP32, Feather, Dashboards, Time Series

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Adafruit IO REST API
REST API at `https://io.adafruit.com/api/v2` providing CRUD across feeds, time-series data points, groups, dashboards, dashboard blocks, triggers, API tokens, permissions/ACL, account activities, and inbound webhooks. Authenticated via the `X-AIO-Key` header or query parameter.

**Human URL:** [https://io.adafruit.com/api/docs/](https://io.adafruit.com/api/docs/)

- [Documentation](https://io.adafruit.com/api/docs/)
- [OpenAPI](openapi/adafruit-io-rest-api-openapi.yml)
- [JSON Schema — Feed](json-schema/adafruit-io-feed-schema.json)
- [JSON Schema — Data Point](json-schema/adafruit-io-data-schema.json)
- [JSON Schema — Dashboard](json-schema/adafruit-io-dashboard-schema.json)
- [JSON-LD Context](json-ld/adafruit-io-context.jsonld)
- [Naftiko Capability — Feeds](capabilities/feeds.yaml)
- [Naftiko Capability — Data](capabilities/data.yaml)
- [Naftiko Capability — Groups](capabilities/groups.yaml)
- [Naftiko Capability — Dashboards](capabilities/dashboards.yaml)
- [Naftiko Capability — Blocks](capabilities/blocks.yaml)
- [Naftiko Capability — Triggers](capabilities/triggers.yaml)
- [Naftiko Capability — Tokens](capabilities/tokens.yaml)
- [Naftiko Capability — Activities](capabilities/activities.yaml)
- [Naftiko Capability — Webhooks](capabilities/webhooks.yaml)

### Adafruit IO MQTT API
MQTT broker at `io.adafruit.com` for publish/subscribe access to feeds and groups. TLS on port 8883, plaintext on 1883, and MQTT-over-WebSocket on port 443. Authenticate with your Adafruit IO username and API key. Supports QoS 0 and QoS 1 only (no QoS 2); the MQTT retain flag is not honored — use the `/get` topic modifier to fetch the last value.

**Human URL:** [https://io.adafruit.com/api/docs/mqtt.html](https://io.adafruit.com/api/docs/mqtt.html)

- [MQTT Documentation](https://io.adafruit.com/api/docs/mqtt.html)
- Topics: `{username}/feeds/{key}`, `{username}/f/{key}` (compact), `{username}/groups/{key}`, `{username}/throttle`, `{username}/errors`

### Adafruit IO Webhooks API
Token-authenticated inbound webhook endpoints that allow third-party services (IFTTT, Zapier, Make, or any HTTP client) to push data into an Adafruit IO feed without an API key.

**Human URL:** [https://io.adafruit.com/api/docs/#webhooks](https://io.adafruit.com/api/docs/#webhooks)

- [Webhook Documentation](https://io.adafruit.com/api/docs/#webhooks)
- [Naftiko Capability — Webhooks](capabilities/webhooks.yaml)

## Plans

| Plan | Price | Data Rate | Retention | Feeds | Dashboards | Actions |
|---|---|---|---|---|---|---|
| Free | $0 | 30 pts/min | 30 days | 10 | 5 | 5 |
| Plus (monthly) | $10/month | 60 pts/min | 60 days | unlimited | unlimited | unlimited |
| Plus (annual) | $99/year | 60 pts/min | 60 days | unlimited | unlimited | unlimited |

## Common Properties

- [Portal — io.adafruit.com](https://io.adafruit.com)
- [Documentation — Adafruit IO API Docs](https://io.adafruit.com/api/docs/)
- [Documentation — MQTT API](https://io.adafruit.com/api/docs/mqtt.html)
- [Documentation — API Cookbook](https://io.adafruit.com/api/docs/cookbook.html)
- [GettingStarted — Adafruit IO Basics Series](https://learn.adafruit.com/series/adafruit-io-basics)
- [GettingStarted — Welcome to Adafruit IO](https://learn.adafruit.com/welcome-to-adafruit-io)
- [Blog](https://io.adafruit.com/blog)
- [ChangeLog](https://io.adafruit.com/blog/changelog/)
- [Forum](https://forums.adafruit.com/viewforum.php?f=56)
- [Forum — Discord #adafruit-io](https://discord.gg/adafruit)
- [SignUp](https://io.adafruit.com/signup)
- [Pricing](https://io.adafruit.com/plus)
- [RateLimits](https://io.adafruit.com/api/docs/#rate-limiting)
- [Errors](https://io.adafruit.com/api/docs/#errors)
- [Authentication](https://io.adafruit.com/api/docs/#authentication)
- [GitHubOrganization](https://github.com/adafruit)
- [SourceCode — Adafruit IO API documentation](https://github.com/adafruit/io-api)
- [SDK — Python](https://github.com/adafruit/Adafruit_IO_Python)
- [SDK — Arduino](https://github.com/adafruit/Adafruit_IO_Arduino)
- [SDK — CircuitPython](https://github.com/adafruit/Adafruit_CircuitPython_AdafruitIO)
- [SDK — Ruby](https://github.com/adafruit/io-client-ruby)
- [SDK — Node.js](https://github.com/adafruit/adafruit-io-node)
- [SDK — Go](https://github.com/adafruit/io-client-go)
- [Tool — Adafruit MQTT Library (Arduino)](https://github.com/adafruit/Adafruit_MQTT_Library)
- [Tool — Adafruit IO TLS Tunnel](https://github.com/adafruit/adafruit-io-node-tunnel)
- [Tool — Swagger Codegen Templates](https://github.com/adafruit/io-swagger-templates)
- [CodeExamples — Adafruit IO Basics Examples](https://github.com/adafruit/adafruit-io-basics)
- [Integrations — IFTTT](https://ifttt.com/adafruit)
- [Integrations — Zapier](https://zapier.com/apps/adafruit-io/integrations)
- [PrivacyPolicy](https://www.adafruit.com/privacy)
- [TermsOfService](https://www.adafruit.com/termsofservice)

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Adafruit IO REST API](openapi/adafruit-io-rest-api-openapi.yml) — full Swagger 2.0 spec converted to OpenAPI 3.0, sourced from [adafruit/io-api](https://github.com/adafruit/io-api).

### JSON Schema

- [Feed](json-schema/adafruit-io-feed-schema.json)
- [Data Point](json-schema/adafruit-io-data-schema.json)
- [Dashboard](json-schema/adafruit-io-dashboard-schema.json)

### JSON Structure

- [Feed Structure](json-structure/adafruit-io-feed-structure.json)
- [Dashboard Structure](json-structure/adafruit-io-dashboard-structure.json)

### JSON-LD

- [Adafruit IO Context](json-ld/adafruit-io-context.jsonld)

### Capabilities (Naftiko)

- [Feeds](capabilities/feeds.yaml)
- [Data](capabilities/data.yaml)
- [Groups](capabilities/groups.yaml)
- [Dashboards](capabilities/dashboards.yaml)
- [Blocks](capabilities/blocks.yaml)
- [Triggers](capabilities/triggers.yaml)
- [Tokens](capabilities/tokens.yaml)
- [Activities](capabilities/activities.yaml)
- [Webhooks](capabilities/webhooks.yaml)

### Spectral Rules

- [Adafruit IO Spectral Ruleset](rules/adafruit-io-rules.yml)

### Vocabulary

- [Adafruit IO Vocabulary](vocabulary/adafruit-io-vocabulary.yml)

### Examples

- [Create a Feed](examples/adafruit-io-create-feed-example.json)
- [Create a Data Point](examples/adafruit-io-create-data-example.json)
- [Batch Data Write](examples/adafruit-io-batch-data-example.json)

### Commercial Artifacts

- [Plans / Pricing](plans/adafruit-io-plans-pricing.yml)
- [Rate Limits](rate-limits/adafruit-io-rate-limits.yml)
- [FinOps Definition](finops/adafruit-io-finops.yml)

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com

**X:** apievangelist

**URL:** [https://apievangelist.com](https://apievangelist.com)
