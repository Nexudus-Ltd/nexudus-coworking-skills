# CoworkerExtraServiceUseHistories

<!-- BEGIN:GENERATED entity=CoworkerExtraServiceUseHistories -->

A **CoworkerExtraServiceUseHistory** is an audit record of how a customer's extra service credits have been consumed. Each record links a `CoworkerExtraService` allowance to the booking that spent it.

Use this entity to review extra service credit consumption across bookings — for example, to verify how many credits a customer used for a specific meeting room reservation or resource booking.

All fields are read-only; this entity is a ledger view and cannot be modified directly.

CoworkerExtraServiceUseHistories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerextraserviceusehistories list --agent` | List all coworkerextraserviceusehistories |
| `nexudus coworkerextraserviceusehistories list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerextraserviceusehistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerextraserviceusehistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerextraserviceusehistories list --booking-from-time <value> --booking-resource-name <value> --agent` | Filter coworkerextraserviceusehistories by properties |
| `nexudus coworkerextraserviceusehistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerextraserviceusehistories list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerextraserviceusehistories get <id> --agent` | Get single coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories create --coworker-extra-service-id <value> --agent` | Create coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories update <id> --name "New Name" --agent` | Update coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories delete <id> --yes --agent` | Delete coworkerextraserviceusehistory (no prompt) |

#### CoworkerExtraServiceUseHistory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-extra-service-id` | long | ID of the coworker extra service linked to this record |
| `--coworker-extra-service-coworker-id` | int | ID of the customer who owns the extra service credit. Read-only, resolved from the linked CoworkerExtraService record. |
| `--from-coworker-extra-service-coworker-id` | range | |
| `--to-coworker-extra-service-coworker-id` | range | |
| `--coworker-extra-service-extra-service-is-printing-credit` | bool | Whether the extra service is a printing credit. Read-only, resolved from the linked ExtraService via CoworkerExtraService. |
| `--coworker-extra-service-extra-service-name` | string | Name of the extra service. Read-only, resolved from the linked ExtraService via CoworkerExtraService. |
| `--coworker-extra-service-expire-date` | DateTime | Expiration date of the extra service credit. Read-only, resolved from the linked CoworkerExtraService record. |
| `--from-coworker-extra-service-expire-date` | range | |
| `--to-coworker-extra-service-expire-date` | range | |
| `--coworker-extra-service-remaining-uses` | int | Number of remaining uses after this consumption. Read-only, resolved from the linked CoworkerExtraService record. |
| `--from-coworker-extra-service-remaining-uses` | range | |
| `--to-coworker-extra-service-remaining-uses` | range | |
| `--coworker-extra-service-is-from-tariff` | bool | Whether the extra service credit came from a plan (tariff) rather than a purchased product. Read-only, resolved from the linked CoworkerExtraService record. |
| `--coworker-extra-service-coworker-product-unique-id` | string | Unique ID (GUID) of the product sale that provided this extra service credit. Read-only, resolved from the linked CoworkerExtraService record. |
| `--booking-id` | long | ID of the booking linked to this record |
| `--booking-from-time` | DateTime | Start time of the booking that consumed the credit |
| `--from-booking-from-time` | range | |
| `--to-booking-from-time` | range | |
| `--booking-to-time` | DateTime | End time of the booking that consumed the credit |
| `--from-booking-to-time` | range | |
| `--to-booking-to-time` | range | |
| `--booking-resource-name` | string | Name of the resource (e.g. meeting room) booked against this credit |
| `--credit-used` | int | Amount of extra service credit consumed by this usage record |
| `--from-credit-used` | range | |
| `--to-credit-used` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerExtraServiceUseHistory sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerExtraServiceUseHistory create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-extra-service-id` | long, required | ID of the coworker extra service linked to this record |
| `--booking-id` | long | ID of the booking linked to this record |

#### CoworkerExtraServiceUseHistory update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-extra-service-id` | long | ID of the coworker extra service linked to this record |
| `--booking-id` | long | ID of the booking linked to this record |

### CoworkerExtraServiceUseHistory (key fields)

`Id`, `BookingFromTime`, `BookingResourceName`, `CreditUsed`

<!-- END:GENERATED entity=CoworkerExtraServiceUseHistories -->
