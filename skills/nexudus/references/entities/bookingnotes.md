# BookingNotes

<!-- BEGIN:GENERATED entity=BookingNotes -->

A **BookingNote** is a text note attached to a `Booking`. These notes are visible to customers and are included in booking confirmation messages.

To add notes that customers cannot see, use the `InternalNotes` field on the `Booking` entity instead.

BookingNotes support Search, Get, Create, Update, Delete.
BookingNotes also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookingnotes list --agent` | List all bookingnotes |
| `nexudus bookingnotes list --id <id> --agent` | Filter by single ID |
| `nexudus bookingnotes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus bookingnotes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus bookingnotes list --added-by <value> --notes <value> --agent` | Filter bookingnotes by properties |
| `nexudus bookingnotes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus bookingnotes get <id> --agent` | Get single bookingnote |
| `nexudus bookingnotes create --booking-id <value> --notes <value> --agent` | Create bookingnote |
| `nexudus bookingnotes update <id> --name "New Name" --agent` | Update bookingnote |
| `nexudus bookingnotes delete <id> --yes --agent` | Delete bookingnote (no prompt) |
| `nexudus bookingnotes run-command <key> <ids> --agent` | Run entity command |

#### BookingNote list filter options

`--booking-id`, `--added-by`, `--notes`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BookingNote create options

`--booking-id` (required), `--added-by`, `--notes` (required)

#### BookingNote update options

`--booking-id`, `--added-by`, `--notes`

### BookingNote (key fields)

`Id`, `AddedBy`, `Notes`

<!-- END:GENERATED entity=BookingNotes -->
