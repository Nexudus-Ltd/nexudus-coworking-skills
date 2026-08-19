# EventWaitingAttendees

<!-- BEGIN:GENERATED entity=EventWaitingAttendees -->

An **EventWaitingAttendee** records a customer on the waiting list for a calendar event that has reached its maximum capacity. When a spot opens up, waiting attendees can be promoted to full attendees.

EventWaitingAttendees support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventwaitingattendees list --agent` | List all eventwaitingattendees |
| `nexudus eventwaitingattendees list --id <id> --agent` | Filter by single ID |
| `nexudus eventwaitingattendees list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventwaitingattendees list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventwaitingattendees list --business-id <value> --calendar-event-id <value> --agent` | Filter eventwaitingattendees by properties |
| `nexudus eventwaitingattendees list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventwaitingattendees list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus eventwaitingattendees get <id> --agent` | Get single eventwaitingattendee |
| `nexudus eventwaitingattendees create --business-id <value> --calendar-event-id <value> --full-name <value> --email <value> --agent` | Create eventwaitingattendee |
| `nexudus eventwaitingattendees update <id> --name "New Name" --agent` | Update eventwaitingattendee |
| `nexudus eventwaitingattendees delete <id> --yes --agent` | Delete eventwaitingattendee (no prompt) |

#### EventWaitingAttendee list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--calendar-event-name` | string | Display name of the linked calendar event (read-only) |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--coworker-full-name` | string | Display name of the linked coworker full (read-only) |
| `--full-name` | string | The full name value for this event waiting attendee |
| `--email` | string | The email value for this event waiting attendee |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EventWaitingAttendee sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EventWaitingAttendee create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--calendar-event-id` | long, required | ID of the calendar event linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--full-name` | string, required | The full name value for this event waiting attendee |
| `--email` | string, required | The email value for this event waiting attendee |

#### EventWaitingAttendee update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--full-name` | string | The full name value for this event waiting attendee |
| `--email` | string | The email value for this event waiting attendee |

#### EventWaitingAttendee PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus eventwaitingattendees update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=EventWaitingAttendees -->
