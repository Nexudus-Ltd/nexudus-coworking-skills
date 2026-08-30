# Sensors

<!-- BEGIN:GENERATED entity=Sensors -->

A sensor is an IoT device for a location that receives or polls environmental and occupancy readings, and can use changed readings to update availability, manage bookings, and send alerts.

Sensors support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus sensors list --agent` | List all sensors |
| `nexudus sensors list --id <id> --agent` | Filter by single ID |
| `nexudus sensors list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus sensors list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus sensors list --business-id <value> --canned-response-id <value> --agent` | Filter sensors by properties |
| `nexudus sensors list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus sensors list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus sensors get <id> --agent` | Get single sensor |
| `nexudus sensors create --business-id <value> --name <value> --reference <value> --sensor-type <value> --data-strategy <value> --agent` | Create sensor |
| `nexudus sensors update <id> --name "New Name" --agent` | Update sensor |
| `nexudus sensors delete <id> --yes --agent` | Delete sensor (no prompt) |

#### Sensor list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the required location that owns this sensor. |
| `--canned-response-id` | long | ID of the optional email template used by sensor alert actions. |
| `--canned-response-name` | string | Display name of the linked canned response (read-only) |
| `--name` | string | Required non-empty display name for the sensor; together with Unit it identifies the sensor within the location. |
| `--reference` | string | Required unique integration reference used to find this sensor within its location; set it when creating the sensor and do not change it later. |
| `--unit` | string | Optional unit label for the sensor reading, such as C, percent, or people; together with Name it identifies the sensor within the location. |
| `--active` | bool | Whether the sensor accepts incoming data and can be polled; inactive sensors do neither. |
| `--sensor-type` | enum | Kind of reading produced by the device: PresenceDetection, PeopleCounter, Temperature, Humidity, Light, Noise, CO2, VolatileOrganicCompounds, HarmfulParticulates, Touch, Water, AtmosphericPressure, Power, OpenClosed, or Other; presence values are normalized to 0 or 1. |
| `--data-strategy` | enum | How readings reach Nexudus: Polling fetches data from PayloadDataPath, while Endpoint, DisruptiveTechnologies, and Pressac receive data through their integrations. |
| `--payload-data-path` | string | URL fetched for a Polling sensor to obtain its payload; polling does nothing when this value is empty. |
| `--action-trigger-function` | string | Optional Flee expression that decides whether a changed reading runs enabled actions; leave empty to run actions for every changed reading, and use payload and sensor as the available context variables. |
| `--value-function` | string | Optional Flee expression that extracts the sensor reading from the incoming payload; leave empty to use payload["value"]. |
| `--action-send-email-alert` | bool | Whether a changed reading that triggers actions sends an operator email alert; repeated alerts are suppressed until a non-triggering reading occurs. |
| `--alert-email-address` | string | Optional email address that receives operator sensor alerts when ActionSendEmailAlert is enabled; must be a valid email address. |
| `--webhook-url` | string | Optional destination URL used by the HTTP request action; it is also logged as the polling source for diagnostics. |
| `--action-update-desk-availability` | bool | Whether triggering readings update availability for the linked floor plan desks. |
| `--action-update-resource-availability` | bool | Whether triggering readings update availability for the linked bookable resources. |
| `--action-update-booking-occupancy` | bool | Whether triggering readings update occupancy for current bookings on linked resources. |
| `--action-send-customer-email-alert` | bool | Whether a changed reading that triggers actions sends a customer alert email; repeated alerts are suppressed until a non-triggering reading occurs. |
| `--action-booking-start` | bool | Whether triggering readings automatically start pending bookings on linked resources. |
| `--action-booking-terminate` | bool | Whether triggering readings automatically terminate active bookings on linked resources. |
| `--action-check-in-or-out` | bool | Whether triggering readings automatically check customers in or out. |
| `--action-make-http-request` | bool | Whether triggering readings send an HTTP request to WebhookUrl. |
| `--show-in-now-dashboard` | bool | Whether the sensor is shown in the Now dashboard for live monitoring. |
| `--show-in-portal` | bool | Whether this active sensor is included in customer portal and app sensor data. |
| `--received-data-on` | DateTime | Read-only UTC date and time when the last valid reading was received; it is set during data ingestion. |
| `--from-received-data-on` | range | |
| `--to-received-data-on` | range | |
| `--last-received-value` | string | Read-only most recent valid reading after ValueFunction processing; change the device payload or ValueFunction instead. |
| `--last-value-triggered-action` | bool | Whether the most recent changed reading passed ActionTriggerFunction and ran enabled actions; it is set during data ingestion. |
| `--battery-level` | int | Read-only battery level reported by the device when available; it is maintained by sensor data ingestion. |
| `--from-battery-level` | range | |
| `--to-battery-level` | range | |
| `--network-signal-strength` | int | Read-only network signal strength reported by the device when available; it is maintained by sensor data ingestion. |
| `--from-network-signal-strength` | range | |
| `--to-network-signal-strength` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Sensor sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Sensor create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the required location that owns this sensor. |
| `--desks` | list, repeat flag | List of floor plan desks whose occupancy and latest sensor value this sensor can update; an empty list means no desks are affected. |
| `--added-desks` | list, repeat flag | The added desks value for this sensor |
| `--removed-desks` | list, repeat flag | The removed desks value for this sensor |
| `--resources` | list, repeat flag | List of bookable resources whose availability, occupancy, and latest sensor value this sensor can update; an empty list means no resources are affected. |
| `--added-resources` | list, repeat flag | The added resources value for this sensor |
| `--removed-resources` | list, repeat flag | The removed resources value for this sensor |
| `--canned-response-id` | long | ID of the optional email template used by sensor alert actions. |
| `--name` | string, required | Required non-empty display name for the sensor; together with Unit it identifies the sensor within the location. |
| `--reference` | string, required | Required unique integration reference used to find this sensor within its location; set it when creating the sensor and do not change it later. |
| `--unit` | string | Optional unit label for the sensor reading, such as C, percent, or people; together with Name it identifies the sensor within the location. |
| `--active` | bool | Whether the sensor accepts incoming data and can be polled; inactive sensors do neither. |
| `--sensor-type` | enum, required | Kind of reading produced by the device: PresenceDetection, PeopleCounter, Temperature, Humidity, Light, Noise, CO2, VolatileOrganicCompounds, HarmfulParticulates, Touch, Water, AtmosphericPressure, Power, OpenClosed, or Other; presence values are normalized to 0 or 1. |
| `--data-strategy` | enum, required | How readings reach Nexudus: Polling fetches data from PayloadDataPath, while Endpoint, DisruptiveTechnologies, and Pressac receive data through their integrations. |
| `--payload-data-path` | string | URL fetched for a Polling sensor to obtain its payload; polling does nothing when this value is empty. |
| `--action-trigger-function` | string | Optional Flee expression that decides whether a changed reading runs enabled actions; leave empty to run actions for every changed reading, and use payload and sensor as the available context variables. |
| `--value-function` | string | Optional Flee expression that extracts the sensor reading from the incoming payload; leave empty to use payload["value"]. |
| `--action-send-email-alert` | bool | Whether a changed reading that triggers actions sends an operator email alert; repeated alerts are suppressed until a non-triggering reading occurs. |
| `--alert-email-address` | string | Optional email address that receives operator sensor alerts when ActionSendEmailAlert is enabled; must be a valid email address. |
| `--webhook-url` | string | Optional destination URL used by the HTTP request action; it is also logged as the polling source for diagnostics. |
| `--action-update-desk-availability` | bool | Whether triggering readings update availability for the linked floor plan desks. |
| `--action-update-resource-availability` | bool | Whether triggering readings update availability for the linked bookable resources. |
| `--action-update-booking-occupancy` | bool | Whether triggering readings update occupancy for current bookings on linked resources. |
| `--action-send-customer-email-alert` | bool | Whether a changed reading that triggers actions sends a customer alert email; repeated alerts are suppressed until a non-triggering reading occurs. |
| `--action-booking-start` | bool | Whether triggering readings automatically start pending bookings on linked resources. |
| `--action-booking-terminate` | bool | Whether triggering readings automatically terminate active bookings on linked resources. |
| `--action-check-in-or-out` | bool | Whether triggering readings automatically check customers in or out. |
| `--action-make-http-request` | bool | Whether triggering readings send an HTTP request to WebhookUrl. |
| `--show-in-now-dashboard` | bool | Whether the sensor is shown in the Now dashboard for live monitoring. |
| `--show-in-portal` | bool | Whether this active sensor is included in customer portal and app sensor data. |

#### Sensor update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the required location that owns this sensor. |
| `--desks` | list, repeat flag | List of floor plan desks whose occupancy and latest sensor value this sensor can update; an empty list means no desks are affected. |
| `--added-desks` | list, repeat flag | The added desks value for this sensor |
| `--removed-desks` | list, repeat flag | The removed desks value for this sensor |
| `--resources` | list, repeat flag | List of bookable resources whose availability, occupancy, and latest sensor value this sensor can update; an empty list means no resources are affected. |
| `--added-resources` | list, repeat flag | The added resources value for this sensor |
| `--removed-resources` | list, repeat flag | The removed resources value for this sensor |
| `--canned-response-id` | long | ID of the optional email template used by sensor alert actions. |
| `--name` | string | Required non-empty display name for the sensor; together with Unit it identifies the sensor within the location. |
| `--unit` | string | Optional unit label for the sensor reading, such as C, percent, or people; together with Name it identifies the sensor within the location. |
| `--active` | bool | Whether the sensor accepts incoming data and can be polled; inactive sensors do neither. |
| `--sensor-type` | enum | Kind of reading produced by the device: PresenceDetection, PeopleCounter, Temperature, Humidity, Light, Noise, CO2, VolatileOrganicCompounds, HarmfulParticulates, Touch, Water, AtmosphericPressure, Power, OpenClosed, or Other; presence values are normalized to 0 or 1. |
| `--data-strategy` | enum | How readings reach Nexudus: Polling fetches data from PayloadDataPath, while Endpoint, DisruptiveTechnologies, and Pressac receive data through their integrations. |
| `--payload-data-path` | string | URL fetched for a Polling sensor to obtain its payload; polling does nothing when this value is empty. |
| `--action-trigger-function` | string | Optional Flee expression that decides whether a changed reading runs enabled actions; leave empty to run actions for every changed reading, and use payload and sensor as the available context variables. |
| `--value-function` | string | Optional Flee expression that extracts the sensor reading from the incoming payload; leave empty to use payload["value"]. |
| `--action-send-email-alert` | bool | Whether a changed reading that triggers actions sends an operator email alert; repeated alerts are suppressed until a non-triggering reading occurs. |
| `--alert-email-address` | string | Optional email address that receives operator sensor alerts when ActionSendEmailAlert is enabled; must be a valid email address. |
| `--webhook-url` | string | Optional destination URL used by the HTTP request action; it is also logged as the polling source for diagnostics. |
| `--action-update-desk-availability` | bool | Whether triggering readings update availability for the linked floor plan desks. |
| `--action-update-resource-availability` | bool | Whether triggering readings update availability for the linked bookable resources. |
| `--action-update-booking-occupancy` | bool | Whether triggering readings update occupancy for current bookings on linked resources. |
| `--action-send-customer-email-alert` | bool | Whether a changed reading that triggers actions sends a customer alert email; repeated alerts are suppressed until a non-triggering reading occurs. |
| `--action-booking-start` | bool | Whether triggering readings automatically start pending bookings on linked resources. |
| `--action-booking-terminate` | bool | Whether triggering readings automatically terminate active bookings on linked resources. |
| `--action-check-in-or-out` | bool | Whether triggering readings automatically check customers in or out. |
| `--action-make-http-request` | bool | Whether triggering readings send an HTTP request to WebhookUrl. |
| `--show-in-now-dashboard` | bool | Whether the sensor is shown in the Now dashboard for live monitoring. |
| `--show-in-portal` | bool | Whether this active sensor is included in customer portal and app sensor data. |

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Resources`, `AddedResources`, `RemovedResources`

#### Sensor enum values

| Option | Valid values |
| ------ | ------------ |
| `--sensor-type` | `1` PresenceDetection, `2` PeopleCounter, `3` Temperature, `4` Humidity, `5` Light, `6` Noise, `7` CO2, `8` VolatileOrganicCompounds, `9` HarmfulParticulates, `10` Touch, `11` Water, `12` AtmosphericPressure, `13` Power, `14` OpenClosed, `99` Other |
| `--data-strategy` | `1` Polling, `2` Endpoint, `3` DisruptiveTechnologies, `4` Pressac |

<!-- END:GENERATED entity=Sensors -->
