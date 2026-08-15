# BookingNotes

<!-- BEGIN:GENERATED entity=BookingNotes -->

A BookingNote is an internal staff note attached to a booking. It records booking activity or comments for staff and may be included in connected admin calendar event descriptions; it is not customer-facing.

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
| `nexudus bookingnotes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus bookingnotes get <id> --agent` | Get single bookingnote |
| `nexudus bookingnotes create --booking-id <value> --notes <value> --agent` | Create bookingnote |
| `nexudus bookingnotes update <id> --name "New Name" --agent` | Update bookingnote |
| `nexudus bookingnotes delete <id> --yes --agent` | Delete bookingnote (no prompt) |
| `nexudus bookingnotes run-command <key> <ids> --agent` | Run entity command |

#### BookingNote list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long | ID of the booking this internal note belongs to. The booking's resource determines this record's location. |
| `--added-by` | string | Name of the user who created the note, assigned automatically from the current user after creation. |
| `--notes` | string | Required free-text internal note for the booking; it is visible to staff and included in connected admin calendar event descriptions, not customer-facing booking messages. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BookingNote sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### BookingNote create options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long, required | ID of the booking this internal note belongs to. The booking's resource determines this record's location. |
| `--added-by` | string | Name of the user who created the note, assigned automatically from the current user after creation. |
| `--notes` | string, required | Required free-text internal note for the booking; it is visible to staff and included in connected admin calendar event descriptions, not customer-facing booking messages. |

#### BookingNote update options

| Option | Type | Description |
| --- | --- | --- |
| `--booking-id` | long | ID of the booking this internal note belongs to. The booking's resource determines this record's location. |
| `--added-by` | string | Name of the user who created the note, assigned automatically from the current user after creation. |
| `--notes` | string | Required free-text internal note for the booking; it is visible to staff and included in connected admin calendar event descriptions, not customer-facing booking messages. |

#### BookingNote PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus bookingnotes update <id> --notes "«PII:BIO:a3f2b1c9»" --agent`

### BookingNote (key fields)

`Id`, `AddedBy`, `Notes`

<!-- END:GENERATED entity=BookingNotes -->
