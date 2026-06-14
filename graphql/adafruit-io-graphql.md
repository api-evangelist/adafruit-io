# Adafruit IO GraphQL Schema

Conceptual GraphQL schema for the Adafruit IO IoT cloud platform. Adafruit IO provides feed-based time-series storage, drag-and-drop dashboards, reactive and scheduled triggers, MQTT and REST APIs, and personal access tokens — all oriented around hobbyist and maker IoT projects.

## Source APIs

- REST API: https://io.adafruit.com/api/docs/
- MQTT API: https://io.adafruit.com/api/docs/mqtt.html
- Webhooks: https://io.adafruit.com/api/docs/#webhooks

## Schema File

- [adafruit-io-schema.graphql](adafruit-io-schema.graphql)

## Type Summary

### Scalars
- `DateTime` — ISO 8601 timestamp
- `JSON` — arbitrary JSON value (used for block properties and batch group publishes)

### Enums
| Enum | Values |
|------|--------|
| `FeedType` | NUMERIC, TEXT, LOCATION, JSON, IMAGE |
| `FeedStatus` | ENABLED, DISABLED, ARCHIVED |
| `BlockType` | TEXT, GAUGE, CHART, SLIDER, BUTTON, TOGGLE, MAP, IMAGE, COLOR, INDICATOR, NUMBER_PAD, SELECTOR, STREAM, BATTERY |
| `TriggerCondition` | EQUAL, GREATER_THAN, LESS_THAN, CHANGED, ON_INSERT |
| `TriggerAction` | NOTIFICATION, WEBHOOK, SMS, VOICE, EMAIL, FEED_WRITE |
| `ScheduleInterval` | MINUTELY, HOURLY, DAILY, WEEKLY, MONTHLY |
| `UserPlan` | FREE, IO_PLUS |
| `LogEntryType` | FEED_CREATED, FEED_UPDATED, FEED_DELETED, DATA_WRITTEN, DASHBOARD_CREATED, DASHBOARD_DELETED, TRIGGER_FIRED, TOKEN_CREATED, TOKEN_REVOKED, LOGIN |

### Named Types

**Feed domain**
- `Feed` — core feed record with key, name, type, status, unit, and group references
- `FeedDetails` — extended feed with webhook token, data count, and embedded group details
- `FeedKey` — key/label pair for feed identification
- `FeedUnit` — unit abbreviation and symbol for feed values
- `FeedStatus` — enabled flag and optional status message

**Data domain**
- `Data` — a single time-series data point with value, timestamps, and optional GPS coordinates
- `DataDetails` — extended data point with parsed value breakdown and expiration info
- `DataValue` — raw, numeric, and text interpretations of a data point value
- `DataCreated` — creation timestamp and Unix epoch representation
- `DataExpiration` — expiration timestamp and retention days for a data point
- `DataLimit` — rate-limit counters (per-minute allowance, current rate, remaining)

**Group domain**
- `Group` — feed group with key, name, visibility, and license
- `GroupDetails` — extended group with embedded feed list and counts
- `GroupKey` — key/label pair for group identification
- `GroupFeeds` — count and list of feeds belonging to a group

**Stream domain**
- `Stream` — a streaming view over a feed's data
- `StreamDetails` — extended stream metadata including last data point and rate
- `StreamData` — individual data point in a stream context

**Dashboard domain**
- `Dashboard` — dashboard with key, name, visibility, and block list
- `DashboardDetails` — extended dashboard with embed URL and detailed block list
- `DashboardKey` — key/label pair for dashboard identification

**Block domain**
- `Block` — generic dashboard visualization block
- `BlockDetails` — block with embedded feed references
- `TextBlock` — text display block with font and color options
- `GaugeBlock` — gauge visualization with min/max range
- `ChartBlock` — time-series chart block with multi-feed support
- `SliderBlock` — range-slider input block
- `ButtonBlock` — momentary button block with press/release values
- `ToggleBlock` — on/off toggle block with configurable values
- `MapBlock` — geographic map block for location feeds
- `ImageBlock` — image display block
- `Color` — RGBA and hex color value

**Webhook domain**
- `FeedWebhook` — inbound webhook token and endpoint URLs for a feed

**Trigger domain**
- `Trigger` — reactive trigger summary (condition, action, feed key, enabled)
- `TriggerDetails` — extended trigger with notify target, webhook URL, and last-fired timestamp
- `TriggerCondition` (enum) — threshold, equality, and change conditions
- `TriggerAction` (enum) — notification channels and feed-write actions

**Schedule domain**
- `Schedule` — scheduled action summary with next-run time
- `ScheduleDetails` — full schedule with interval, time-of-day, timezone, and action payload
- `ScheduleAction` — the action executed when a schedule fires

**Throttle / Limit domain**
- `Throttle` — current throttle state (active, rate, remaining)
- `ThrottleDetails` — full throttle record with reset timestamp
- `Limit` — generic limit record covering feeds, dashboards, actions, etc.

**User domain**
- `User` — lightweight user record with plan
- `UserDetails` — full user profile with counts and plan details
- `UserPlanDetails` — plan entitlements (feed limit, retention days, data rate, price)

**Activity / Logging domain**
- `LogEntry` — single activity log entry with type, message, and IP
- `ActivityLog` — paginated collection of log entries

**Credentials domain**
- `APIKey` — masked API key record
- `Token` — personal access token with scopes and expiry
- `MQTTCredentials` — host, ports, username, and password for MQTT connections

**Pagination**
- `PageInfo` — cursor-based pagination info
- `FeedConnection`, `DataConnection`, `GroupConnection`, `DashboardConnection`, `TriggerConnection`, `TokenConnection` — paginated list wrappers

**Input types**
- `FeedInput`, `FeedUnitInput`, `DataInput`, `GroupInput`, `DashboardInput`, `BlockInput`, `TriggerInput`, `ScheduleInput`, `ScheduleActionInput`, `TokenInput`

## Operations

### Queries
- User: `currentUser`
- Feeds: `feeds`, `feed`, `feedByKey`
- Data: `feedData`, `feedDataPoint`, `feedLastValue`, `feedFirstValue`, `feedPreviousValue`, `feedNextValue`, `feedRetainValue`, `feedChartData`
- Groups: `groups`, `group`, `groupFeeds`
- Dashboards: `dashboards`, `dashboard`, `dashboardBlocks`, `dashboardBlock`
- Triggers: `triggers`, `trigger`
- Schedules: `schedules`, `schedule`
- Throttle & Limits: `throttle`, `limits`
- Activity: `activities`
- Tokens: `tokens`, `token`
- MQTT: `mqttCredentials`

### Mutations
- Feed CRUD: `createFeed`, `updateFeed`, `deleteFeed`
- Data writes: `createDataPoint`, `createDataPoints`, `deleteDataPoint`
- Group CRUD + membership: `createGroup`, `updateGroup`, `deleteGroup`, `addFeedToGroup`, `removeFeedFromGroup`, `publishToGroup`
- Dashboard CRUD: `createDashboard`, `updateDashboard`, `deleteDashboard`
- Block CRUD: `createBlock`, `updateBlock`, `deleteBlock`
- Trigger CRUD: `createTrigger`, `updateTrigger`, `deleteTrigger`
- Schedule CRUD: `createSchedule`, `updateSchedule`, `deleteSchedule`
- Token management: `createToken`, `revokeToken`

### Subscriptions
- `feedDataUpdated` — real-time data for a single feed (maps to MQTT feed topic)
- `groupDataUpdated` — real-time data for all feeds in a group (maps to MQTT group topic)
- `throttleUpdated` — rate-limit pressure notifications (maps to MQTT throttle topic)
- `triggerFired` — notifications when a reactive trigger fires
