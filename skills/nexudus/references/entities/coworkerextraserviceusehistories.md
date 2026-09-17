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
| `--coworker-extra-service-coworker-id` | int | Display value for CoworkerExtraService.Coworker.Id. |
| `--from-coworker-extra-service-coworker-id` | range | |
| `--to-coworker-extra-service-coworker-id` | range | |
| `--coworker-extra-service-extra-service-is-printing-credit` | bool | Display value for CoworkerExtraService.ExtraService.IsPrintingCredit. |
| `--coworker-extra-service-extra-service-name` | string | Display value for CoworkerExtraService.ExtraService.Name. |
| `--coworker-extra-service-expire-date` | DateTime | Display value for CoworkerExtraService.ExpireDate. |
| `--from-coworker-extra-service-expire-date` | range | |
| `--to-coworker-extra-service-expire-date` | range | |
| `--coworker-extra-service-remaining-uses` | int | Display value for CoworkerExtraService.RemainingUses. |
| `--from-coworker-extra-service-remaining-uses` | range | |
| `--to-coworker-extra-service-remaining-uses` | range | |
| `--coworker-extra-service-is-from-tariff` | bool | Display value for CoworkerExtraService.IsFromTariff. |
| `--coworker-extra-service-coworker-product-unique-id` | string | Display value for CoworkerExtraService.CoworkerProductUniqueId. |
| `--booking-id` | long | ID of the booking linked to this record |
| `--booking-from-time` | DateTime | Display value for Booking.FromTime. |
| `--from-booking-from-time` | range | |
| `--to-booking-from-time` | range | |
| `--booking-to-time` | DateTime | Display value for Booking.ToTime. |
| `--from-booking-to-time` | range | |
| `--to-booking-to-time` | range | |
| `--booking-resource-name` | string | Display value for Booking.Resource.Name. |
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
