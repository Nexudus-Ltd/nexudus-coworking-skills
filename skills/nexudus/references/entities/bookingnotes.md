# BookingNotes

<!-- BEGIN:GENERATED entity=BookingNotes -->

A **BookingNote** is a text note attached to a `Booking`. These notes are visible to customers and are included in booking confirmation messages.

To add notes that customers cannot see, use the `InternalNotes` field on the `Booking` entity instead.

BookingNotes support Search, Get, Create, Update, Delete.
BookingNotes also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookingnotes list --agent` | List all bookingnotes |
| `nexudus bookingnotes list --query "search" --agent` | Search bookingnotes by name |
| `nexudus bookingnotes list --page 2 --size 10 --agent` | Paginated list |
| `nexudus bookingnotes get <id> --agent` | Get single bookingnote |
| `nexudus bookingnotes create --booking-id <value> --agent` | Create bookingnote |
| `nexudus bookingnotes update <id> --name "New Name" --agent` | Update bookingnote |
| `nexudus bookingnotes delete <id> --yes --agent` | Delete bookingnote (no prompt) |
| `nexudus bookingnotes run-command <key> <ids> --agent` | Run entity command |

#### BookingNote create options

`--booking-id` (required), `--notes`

#### BookingNote update options

`--booking-id`, `--notes`

### BookingNote (key fields)

`Id`, `BookingId`, `AddedBy`, `Notes`

<!-- END:GENERATED entity=BookingNotes -->
