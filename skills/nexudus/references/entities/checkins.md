# Checkins

<!-- BEGIN:GENERATED entity=Checkins -->

A Checkin records a customer's access to a location using an eligible pass. The system first selects an eligible customer or shared pass; when none is available, it creates a customer pay-as-you-go pass only when the location enables pay-as-you-go and has a valid pass for that customer type. A pay-as-you-go check-in starts with no charge and, at checkout, is charged by duration or fixed pass price subject to the location's daily minimum and maximum settings. Check-ins can be opened or closed manually or through access, network, sensor, tile, or booking integrations.

Checkins support Search, Get, Create, Update, Delete.
Checkins also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus checkins list --agent` | List all checkins |
| `nexudus checkins list --id <id> --agent` | Filter by single ID |
| `nexudus checkins list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus checkins list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus checkins list --coworker-full-name <value> --business-name <value> --agent` | Filter checkins by properties |
| `nexudus checkins list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus checkins list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus checkins get <id> --agent` | Get single checkin |
| `nexudus checkins create --business-id <value> --from-time <value> --agent` | Create checkin |
| `nexudus checkins update <id> --name "New Name" --agent` | Update checkin |
| `nexudus checkins delete <id> --yes --agent` | Delete checkin (no prompt) |
| `nexudus checkins run-command <key> <ids> --agent` | Run entity command |

#### Checkin list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer checking in. The customer must be active; the system first uses an eligible customer or shared pass, then can fall back to an eligible pay-as-you-go pass when the location allows it. |
| `--coworker-full-name` | string | Full name of the checked-in customer |
| `--business-id` | long | ID of the location where the customer checked in. The Admin Agent supplies the current location for create and update operations. |
| `--business-name` | string | Name of the location where the check-in takes place |
| `--source` | enum | Read-only origin of the check-in: Manual, DoorAccess, NetworkActivity, Tile, Sensor, or Booking. New manual records default to Manual. |
| `--from-time` | DateTime | Check-in start date and time, stored in UTC and rounded to the nearest 15 minutes. It must be earlier than ToTime when a checkout time is provided. |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | Optional checkout date and time, stored in UTC and rounded to the nearest 15 minutes. Leave empty to keep the check-in open; when set, it must be later than FromTime. |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--last-activity` | DateTime | Internal UTC timestamp of the most recent activity reported by a network or access-control integration for this open check-in. |
| `--from-last-activity` | range | |
| `--to-last-activity` | range | |
| `--mac-addresses` | string | Internal comma-separated device MAC addresses captured by a network-activity check-in; this network identifier is managed by integrations. |
| `--teams-at-checkin` | string | System-generated comma-separated snapshot of the customer's team names when the check-in was created. |
| `--tariff-at-checkin` | string | System-generated comma-separated snapshot of the customer's active plan names when the check-in was created. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Checkin sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `FromTime` descending. If no `--order-by` is specified, the API returns results ordered by `FromTime` (descending).

#### Checkin create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer checking in. The customer must be active; the system first uses an eligible customer or shared pass, then can fall back to an eligible pay-as-you-go pass when the location allows it. |
| `--business-id` | long, required | ID of the location where the customer checked in. The Admin Agent supplies the current location for create and update operations. |
| `--from-time` | DateTime, required | Check-in start date and time, stored in UTC and rounded to the nearest 15 minutes. It must be earlier than ToTime when a checkout time is provided. |
| `--to-time` | DateTime | Optional checkout date and time, stored in UTC and rounded to the nearest 15 minutes. Leave empty to keep the check-in open; when set, it must be later than FromTime. |
| `--last-activity` | DateTime | Internal UTC timestamp of the most recent activity reported by a network or access-control integration for this open check-in. |
| `--mac-addresses` | string | Internal comma-separated device MAC addresses captured by a network-activity check-in; this network identifier is managed by integrations. |
| `--teams-at-checkin` | string | System-generated comma-separated snapshot of the customer's team names when the check-in was created. |
| `--tariff-at-checkin` | string | System-generated comma-separated snapshot of the customer's active plan names when the check-in was created. |

#### Checkin update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer checking in. The customer must be active; the system first uses an eligible customer or shared pass, then can fall back to an eligible pay-as-you-go pass when the location allows it. |
| `--business-id` | long | ID of the location where the customer checked in. The Admin Agent supplies the current location for create and update operations. |
| `--from-time` | DateTime | Check-in start date and time, stored in UTC and rounded to the nearest 15 minutes. It must be earlier than ToTime when a checkout time is provided. |
| `--to-time` | DateTime | Optional checkout date and time, stored in UTC and rounded to the nearest 15 minutes. Leave empty to keep the check-in open; when set, it must be later than FromTime. |
| `--last-activity` | DateTime | Internal UTC timestamp of the most recent activity reported by a network or access-control integration for this open check-in. |
| `--mac-addresses` | string | Internal comma-separated device MAC addresses captured by a network-activity check-in; this network identifier is managed by integrations. |
| `--teams-at-checkin` | string | System-generated comma-separated snapshot of the customer's team names when the check-in was created. |
| `--tariff-at-checkin` | string | System-generated comma-separated snapshot of the customer's active plan names when the check-in was created. |

#### Checkin PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus checkins update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### Checkin (key fields)

`Id`, `CoworkerFullName`, `BusinessName`, `Source`, `FromTime`, `ToTime`

<!-- END:GENERATED entity=Checkins -->
