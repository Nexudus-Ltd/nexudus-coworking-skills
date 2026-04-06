# Sensors

<!-- BEGIN:GENERATED entity=Sensors -->

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

`--business-id`, `--canned-response-id`, `--name`, `--reference`, `--unit`, `--active`, `--sensor-type`, `--data-strategy`, `--payload-data-path`, `--action-trigger-function`, `--value-function`, `--action-send-email-alert`, `--alert-email-address`, `--webhook-url`, `--action-update-desk-availability`, `--action-update-resource-availability`, `--action-update-booking-occupancy`, `--action-send-customer-email-alert`, `--action-booking-start`, `--action-booking-terminate`, `--action-check-in-or-out`, `--action-make-http-request`, `--show-in-now-dashboard`, `--show-in-portal`, `--shared-secret`, `--api-key`, `--username`, `--password`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Sensor create options

`--business-id` (required), `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--canned-response-id`, `--name` (required), `--reference` (required), `--unit`, `--active`, `--sensor-type` (required), `--data-strategy` (required), `--payload-data-path`, `--action-trigger-function`, `--value-function`, `--action-send-email-alert`, `--alert-email-address`, `--webhook-url`, `--action-update-desk-availability`, `--action-update-resource-availability`, `--action-update-booking-occupancy`, `--action-send-customer-email-alert`, `--action-booking-start`, `--action-booking-terminate`, `--action-check-in-or-out`, `--action-make-http-request`, `--show-in-now-dashboard`, `--show-in-portal`, `--shared-secret`, `--api-key`, `--username`, `--password`

#### Sensor update options

`--business-id`, `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--canned-response-id`, `--name`, `--unit`, `--active`, `--sensor-type`, `--data-strategy`, `--payload-data-path`, `--action-trigger-function`, `--value-function`, `--action-send-email-alert`, `--alert-email-address`, `--webhook-url`, `--action-update-desk-availability`, `--action-update-resource-availability`, `--action-update-booking-occupancy`, `--action-send-customer-email-alert`, `--action-booking-start`, `--action-booking-terminate`, `--action-check-in-or-out`, `--action-make-http-request`, `--show-in-now-dashboard`, `--show-in-portal`, `--shared-secret`, `--api-key`, `--username`, `--password`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=Sensors -->
