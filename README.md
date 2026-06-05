# Adafruit IO (adafruit-io)

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
