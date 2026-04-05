# BookingAvailabilityExceptions

<!-- BEGIN:GENERATED entity=BookingAvailabilityExceptions -->

A **BookingAvailabilityException** blocks one or more `Resource`s from being booked during a specific date/time window. When a user tries to book a blocked resource, they see the configured `Message` instead of available time slots.

Use exceptions for holidays, maintenance periods, or any other reason a resource should be temporarily unavailable. Set `EveryYear` to `true` for recurring annual closures (e.g. public holidays).


BookingAvailabilityExceptions support Search, Get, Create, Update, Delete.
BookingAvailabilityExceptions also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookingavailabilityexceptions list --agent` | List all bookingavailabilityexceptions |
| `nexudus bookingavailabilityexceptions list --id <id> --agent` | Filter by single ID |
| `nexudus bookingavailabilityexceptions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus bookingavailabilityexceptions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus bookingavailabilityexceptions list --from-time <value> --to-time <value> --agent` | Filter bookingavailabilityexceptions by properties |
| `nexudus bookingavailabilityexceptions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus bookingavailabilityexceptions get <id> --agent` | Get single bookingavailabilityexception |
| `nexudus bookingavailabilityexceptions create --business-id <value> --from-time <value> --to-time <value> --message <value> --agent` | Create bookingavailabilityexception |
| `nexudus bookingavailabilityexceptions update <id> --name "New Name" --agent` | Update bookingavailabilityexception |
| `nexudus bookingavailabilityexceptions delete <id> --yes --agent` | Delete bookingavailabilityexception (no prompt) |
| `nexudus bookingavailabilityexceptions run-command <key> <ids> --agent` | Run entity command |

#### BookingAvailabilityException list filter options

`--business-id`, `--from-time`, `--from-from-time` (range), `--to-from-time` (range), `--to-time`, `--from-to-time` (range), `--to-to-time` (range), `--message`, `--active`, `--every-year`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BookingAvailabilityException create options

`--business-id` (required), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--from-time` (required), `--to-time` (required), `--message` (required), `--active`, `--every-year`

#### BookingAvailabilityException update options

`--business-id`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--from-time`, `--to-time`, `--message`, `--active`, `--every-year`

### BookingAvailabilityException (key fields)

`Id`, `BusinessName`, `FromTime`, `ToTime`, `Message`, `Active`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=BookingAvailabilityExceptions -->
