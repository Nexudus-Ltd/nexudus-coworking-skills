# BookingVisitors

<!-- BEGIN:GENERATED entity=BookingVisitors -->

A **BookingVisitor** links a `Visitor` to a `Booking`, representing a guest associated with that booking.

Visitors can only be added to bookings that are associated with a customer (`Booking.CoworkerId` is not null).

When a visitor is added to a booking, they may receive a booking confirmation email and a visitor invite email, depending on the notification settings configured for the location of the booked resource.

BookingVisitors support Search, Get, Create, Update, Delete.
BookingVisitors also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookingvisitors list --agent` | List all bookingvisitors |
| `nexudus bookingvisitors list --id <id> --agent` | Filter by single ID |
| `nexudus bookingvisitors list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus bookingvisitors list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus bookingvisitors list --booking-id <value> --visitor-id <value> --agent` | Filter bookingvisitors by properties |
| `nexudus bookingvisitors list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus bookingvisitors get <id> --agent` | Get single bookingvisitor |
| `nexudus bookingvisitors create --booking-id <value> --visitor-id <value> --agent` | Create bookingvisitor |
| `nexudus bookingvisitors update <id> --name "New Name" --agent` | Update bookingvisitor |
| `nexudus bookingvisitors delete <id> --yes --agent` | Delete bookingvisitor (no prompt) |
| `nexudus bookingvisitors run-command <key> <ids> --agent` | Run entity command |

#### BookingVisitor list filter options

`--booking-id`, `--visitor-id`

#### BookingVisitor create options

`--booking-id` (required), `--visitor-id` (required)

#### BookingVisitor update options

`--booking-id`, `--visitor-id`

### BookingVisitor (key fields)

`Id`, `VisitorFullName`

<!-- END:GENERATED entity=BookingVisitors -->
