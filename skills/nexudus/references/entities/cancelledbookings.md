# CancelledBookings

<!-- BEGIN:GENERATED entity=CancelledBookings -->

A **CancelledBooking** is a read-only snapshot of a booking that was removed from the calendar. When a booking is cancelled, the system preserves its details — resource, coworker, time range, price, and cancellation metadata — so they remain available for reporting and auditing.

Cancelled bookings cannot be created or modified through the API; they are generated automatically when an active `Booking` is cancelled. Use `list` and `get` to query cancellation history.

The `CancellationReason` field indicates why the booking was removed. Possible reasons include the customer no longer needing the booking, cost concerns, rebooking for a different time, failure to pay upfront, automated cancellation due to not checking in, and others.

CancelledBookings support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus cancelledbookings list --agent` | List all cancelledbookings |
| `nexudus cancelledbookings list --query "search" --agent` | Search cancelledbookings by name |
| `nexudus cancelledbookings list --page 2 --size 10 --agent` | Paginated list |
| `nexudus cancelledbookings get <id> --agent` | Get single cancelledbooking |

### CancelledBooking (key fields)

`Id`, `ResourceId`, `ResourceName`, `CoworkerId`, `CoworkerFullName`, `FromTime`, `ToTime`, `CancellationReason`, `CancelledOn`

<!-- END:GENERATED entity=CancelledBookings -->
