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
| `nexudus coworkerextraserviceusehistories list --coworker-extra-service-id <value> --booking-id <value> --agent` | Filter coworkerextraserviceusehistories by properties |
| `nexudus coworkerextraserviceusehistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerextraserviceusehistories get <id> --agent` | Get single coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories create --coworker-extra-service-id <value> --agent` | Create coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories update <id> --name "New Name" --agent` | Update coworkerextraserviceusehistory |
| `nexudus coworkerextraserviceusehistories delete <id> --yes --agent` | Delete coworkerextraserviceusehistory (no prompt) |

#### CoworkerExtraServiceUseHistory list filter options

`--coworker-extra-service-id` (long), `--booking-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerExtraServiceUseHistory create options

`--coworker-extra-service-id` (long, required), `--booking-id` (long)

#### CoworkerExtraServiceUseHistory update options

`--coworker-extra-service-id` (long), `--booking-id` (long)

### CoworkerExtraServiceUseHistory (key fields)

`Id`, `BookingFromTime`, `BookingResourceName`, `CreditUsed`

<!-- END:GENERATED entity=CoworkerExtraServiceUseHistories -->
