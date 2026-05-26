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

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long |  |
| `--visitor-id` | long |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BookingVisitor create options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long, required |  |
| `--visitor-id` | long, required |  |

#### BookingVisitor update options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long |  |
| `--visitor-id` | long |  |

#### BookingVisitor PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--visitor-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--visitor-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--visitor-phone-number` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--visitor-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus bookingvisitors update <id> --visitor-full-name "«PII:NAME:a3f2b1c9»" --agent`

### BookingVisitor (key fields)

`Id`, `VisitorFullName`

<!-- END:GENERATED entity=BookingVisitors -->
