# Sensors

<!-- BEGIN:GENERATED entity=Sensors -->

A **Sensor** represents a physical IoT sensor deployed in a location for monitoring environmental conditions or occupancy. Sensors can detect presence, count people, measure temperature, humidity, noise, CO2 levels, and other metrics.

Sensors support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus sensors list --agent` | List all sensors |
| `nexudus sensors list --id <id> --agent` | Filter by single ID |
| `nexudus sensors list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus sensors list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus sensors list --business-id <value> --canned-response-id <value> --agent` | Filter sensors by properties |
| `nexudus sensors list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus sensors get <id> --agent` | Get single sensor |
| `nexudus sensors create --business-id <value> --name <value> --reference <value> --sensor-type <value> --data-strategy <value> --agent` | Create sensor |
| `nexudus sensors update <id> --name "New Name" --agent` | Update sensor |
| `nexudus sensors delete <id> --yes --agent` | Delete sensor (no prompt) |

#### Sensor list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--canned-response-id` | long | ID of the canned response linked to this record |
| `--name` | string | The name value for this sensor |
| `--reference` | string | The reference value for this sensor |
| `--unit` | string | The unit value for this sensor |
| `--active` | bool | Whether this sensor is currently active |
| `--sensor-type` | enum | The sensor type value for this sensor |
| `--data-strategy` | enum | The data strategy value for this sensor |
| `--payload-data-path` | string | The payload data path value for this sensor |
| `--action-trigger-function` | string | The action trigger function value for this sensor |
| `--value-function` | string | The value function value for this sensor |
| `--action-send-email-alert` | bool | Whether action send email alert is enabled |
| `--alert-email-address` | string | The alert email address value for this sensor |
| `--webhook-url` | string | The webhook url value for this sensor |
| `--action-update-desk-availability` | bool | Whether action update desk availability is enabled |
| `--action-update-resource-availability` | bool | Whether action update resource availability is enabled |
| `--action-update-booking-occupancy` | bool | Whether action update booking occupancy is enabled |
| `--action-send-customer-email-alert` | bool | Whether action send customer email alert is enabled |
| `--action-booking-start` | bool | Whether action booking start is enabled |
| `--action-booking-terminate` | bool | Whether action booking terminate is enabled |
| `--action-check-in-or-out` | bool | Whether action check in or out is enabled |
| `--action-make-http-request` | bool | Whether action make http request is enabled |
| `--show-in-now-dashboard` | bool | Whether show in now dashboard is enabled |
| `--show-in-portal` | bool | Whether show in portal is enabled |
| `--shared-secret` | string | The shared secret value for this sensor |
| `--api-key` | string | The api key value for this sensor |
| `--username` | string | The username value for this sensor |
| `--password` | string | The password value for this sensor |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Sensor create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--desks` | list, repeat flag | List of desks linked to this record |
| `--added-desks` | list, repeat flag | The added desks value for this sensor |
| `--removed-desks` | list, repeat flag | The removed desks value for this sensor |
| `--resources` | list, repeat flag | List of resources linked to this record |
| `--added-resources` | list, repeat flag | The added resources value for this sensor |
| `--removed-resources` | list, repeat flag | The removed resources value for this sensor |
| `--canned-response-id` | long | ID of the canned response linked to this record |
| `--name` | string, required | The name value for this sensor |
| `--reference` | string, required | The reference value for this sensor |
| `--unit` | string | The unit value for this sensor |
| `--active` | bool | Whether this sensor is currently active |
| `--sensor-type` | enum, required | The sensor type value for this sensor |
| `--data-strategy` | enum, required | The data strategy value for this sensor |
| `--payload-data-path` | string | The payload data path value for this sensor |
| `--action-trigger-function` | string | The action trigger function value for this sensor |
| `--value-function` | string | The value function value for this sensor |
| `--action-send-email-alert` | bool | Whether action send email alert is enabled |
| `--alert-email-address` | string | The alert email address value for this sensor |
| `--webhook-url` | string | The webhook url value for this sensor |
| `--action-update-desk-availability` | bool | Whether action update desk availability is enabled |
| `--action-update-resource-availability` | bool | Whether action update resource availability is enabled |
| `--action-update-booking-occupancy` | bool | Whether action update booking occupancy is enabled |
| `--action-send-customer-email-alert` | bool | Whether action send customer email alert is enabled |
| `--action-booking-start` | bool | Whether action booking start is enabled |
| `--action-booking-terminate` | bool | Whether action booking terminate is enabled |
| `--action-check-in-or-out` | bool | Whether action check in or out is enabled |
| `--action-make-http-request` | bool | Whether action make http request is enabled |
| `--show-in-now-dashboard` | bool | Whether show in now dashboard is enabled |
| `--show-in-portal` | bool | Whether show in portal is enabled |
| `--shared-secret` | string | The shared secret value for this sensor |
| `--api-key` | string | The api key value for this sensor |
| `--username` | string | The username value for this sensor |
| `--password` | string | The password value for this sensor |

#### Sensor update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--desks` | list, repeat flag | List of desks linked to this record |
| `--added-desks` | list, repeat flag | The added desks value for this sensor |
| `--removed-desks` | list, repeat flag | The removed desks value for this sensor |
| `--resources` | list, repeat flag | List of resources linked to this record |
| `--added-resources` | list, repeat flag | The added resources value for this sensor |
| `--removed-resources` | list, repeat flag | The removed resources value for this sensor |
| `--canned-response-id` | long | ID of the canned response linked to this record |
| `--name` | string | The name value for this sensor |
| `--unit` | string | The unit value for this sensor |
| `--active` | bool | Whether this sensor is currently active |
| `--sensor-type` | enum | The sensor type value for this sensor |
| `--data-strategy` | enum | The data strategy value for this sensor |
| `--payload-data-path` | string | The payload data path value for this sensor |
| `--action-trigger-function` | string | The action trigger function value for this sensor |
| `--value-function` | string | The value function value for this sensor |
| `--action-send-email-alert` | bool | Whether action send email alert is enabled |
| `--alert-email-address` | string | The alert email address value for this sensor |
| `--webhook-url` | string | The webhook url value for this sensor |
| `--action-update-desk-availability` | bool | Whether action update desk availability is enabled |
| `--action-update-resource-availability` | bool | Whether action update resource availability is enabled |
| `--action-update-booking-occupancy` | bool | Whether action update booking occupancy is enabled |
| `--action-send-customer-email-alert` | bool | Whether action send customer email alert is enabled |
| `--action-booking-start` | bool | Whether action booking start is enabled |
| `--action-booking-terminate` | bool | Whether action booking terminate is enabled |
| `--action-check-in-or-out` | bool | Whether action check in or out is enabled |
| `--action-make-http-request` | bool | Whether action make http request is enabled |
| `--show-in-now-dashboard` | bool | Whether show in now dashboard is enabled |
| `--show-in-portal` | bool | Whether show in portal is enabled |
| `--shared-secret` | string | The shared secret value for this sensor |
| `--api-key` | string | The api key value for this sensor |
| `--username` | string | The username value for this sensor |
| `--password` | string | The password value for this sensor |

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Resources`, `AddedResources`, `RemovedResources`

#### Sensor enum values

| Option | Valid values |
| ------ | ------------ |
| `--sensor-type` | `1` PresenceDetection, `2` PeopleCounter, `3` Temperature, `4` Humidity, `5` Light, `6` Noise, `7` CO2, `8` VolatileOrganicCompounds, `9` HarmfulParticulates, `10` Touch, `11` Water, `12` AtmosphericPressure, `13` Power, `14` OpenClosed, `99` Other |
| `--data-strategy` | `1` Polling, `2` Endpoint, `3` DisruptiveTechnologies, `4` Pressac |

<!-- END:GENERATED entity=Sensors -->
