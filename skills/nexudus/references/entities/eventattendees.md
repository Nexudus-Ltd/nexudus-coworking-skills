# EventAttendees

<!-- BEGIN:GENERATED entity=EventAttendees -->

EventAttendees support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventattendees list --agent` | List all eventattendees |
| `nexudus eventattendees list --id <id> --agent` | Filter by single ID |
| `nexudus eventattendees list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventattendees list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventattendees list --business-id <value> --calendar-event-id <value> --agent` | Filter eventattendees by properties |
| `nexudus eventattendees list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventattendees get <id> --agent` | Get single eventattendee |
| `nexudus eventattendees create --business-id <value> --calendar-event-id <value> --event-product-id <value> --full-name <value> --email <value> --agent` | Create eventattendee |
| `nexudus eventattendees update <id> --name "New Name" --agent` | Update eventattendee |
| `nexudus eventattendees delete <id> --yes --agent` | Delete eventattendee (no prompt) |

#### EventAttendee list filter options

`--business-id`, `--calendar-event-id`, `--event-product-id`, `--coworker-id`, `--full-name`, `--email`, `--purchase-order`, `--checked-in`, `--checked-in-date`, `--invoiced`, `--billed`, `--created-on-local`, `--checked-in-date-local`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--reminded`, `--zoom-event-data`, `--zoom-participant-id`, `--is-sent`

#### EventAttendee create options

`--business-id` (required), `--calendar-event-id` (required), `--event-product-id` (required), `--coworker-id`, `--full-name` (required), `--email` (required), `--purchase-order`, `--checked-in`, `--checked-in-date`, `--invoiced`, `--billed`, `--created-on-local`, `--checked-in-date-local`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--reminded`, `--zoom-event-data`, `--zoom-participant-id`, `--is-sent`

#### EventAttendee update options

`--business-id`, `--calendar-event-id`, `--event-product-id`, `--coworker-id`, `--full-name`, `--email`, `--purchase-order`, `--checked-in`, `--checked-in-date`, `--billed`, `--created-on-local`, `--checked-in-date-local`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--reminded`, `--zoom-event-data`, `--zoom-participant-id`, `--is-sent`

<!-- END:GENERATED entity=EventAttendees -->
