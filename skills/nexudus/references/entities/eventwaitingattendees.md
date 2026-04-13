# EventWaitingAttendees

<!-- BEGIN:GENERATED entity=EventWaitingAttendees -->

EventWaitingAttendees support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventwaitingattendees list --agent` | List all eventwaitingattendees |
| `nexudus eventwaitingattendees list --id <id> --agent` | Filter by single ID |
| `nexudus eventwaitingattendees list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventwaitingattendees list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventwaitingattendees list --business-id <value> --calendar-event-id <value> --agent` | Filter eventwaitingattendees by properties |
| `nexudus eventwaitingattendees list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventwaitingattendees get <id> --agent` | Get single eventwaitingattendee |
| `nexudus eventwaitingattendees create --business-id <value> --calendar-event-id <value> --full-name <value> --email <value> --agent` | Create eventwaitingattendee |
| `nexudus eventwaitingattendees update <id> --name "New Name" --agent` | Update eventwaitingattendee |
| `nexudus eventwaitingattendees delete <id> --yes --agent` | Delete eventwaitingattendee (no prompt) |

#### EventWaitingAttendee list filter options

`--business-id` (long), `--calendar-event-id` (long), `--coworker-id` (long), `--full-name`, `--email`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EventWaitingAttendee create options

`--business-id` (long, required), `--calendar-event-id` (long, required), `--coworker-id` (long), `--full-name` (required), `--email` (required)

#### EventWaitingAttendee update options

`--business-id` (long), `--calendar-event-id` (long), `--coworker-id` (long), `--full-name`, `--email`

<!-- END:GENERATED entity=EventWaitingAttendees -->
