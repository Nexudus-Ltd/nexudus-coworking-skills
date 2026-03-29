# BookingAvailabilityExceptions

<!-- BEGIN:GENERATED entity=BookingAvailabilityExceptions -->

A **BookingAvailabilityException** blocks one or more `Resource`s from being booked during a specific date/time window. When a user tries to book a blocked resource, they see the configured `Message` instead of available time slots.

Use exceptions for holidays, maintenance periods, or any other reason a resource should be temporarily unavailable. Set `EveryYear` to `true` for recurring annual closures (e.g. public holidays).


BookingAvailabilityExceptions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus bookingavailabilityexceptions list --agent` | List all bookingavailabilityexceptions |
| `nexudus bookingavailabilityexceptions list --query "search" --agent` | Search bookingavailabilityexceptions by name |
| `nexudus bookingavailabilityexceptions list --page 2 --size 10 --agent` | Paginated list |
| `nexudus bookingavailabilityexceptions get <id> --agent` | Get single bookingavailabilityexception |
| `nexudus bookingavailabilityexceptions create --business <value> --from-time <value> --to-time <value> --agent` | Create bookingavailabilityexception |
| `nexudus bookingavailabilityexceptions update <id> --name "New Name" --agent` | Update bookingavailabilityexception |
| `nexudus bookingavailabilityexceptions delete <id> --yes --agent` | Delete bookingavailabilityexception (no prompt) |

#### BookingAvailabilityException create options

`--business` (required), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--from-time` (required), `--to-time` (required), `--message`, `--active`, `--every-year`

#### BookingAvailabilityException update options

`--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--from-time`, `--to-time`, `--message`, `--active`, `--every-year`

### BookingAvailabilityException (key fields)

`Id`, `BusinessId`, `BusinessName`, `FromTime`, `ToTime`, `Message`, `Active`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=BookingAvailabilityExceptions -->
