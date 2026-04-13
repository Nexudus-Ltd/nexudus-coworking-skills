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

`--business-id` (long), `--calendar-event-id` (long), `--event-product-id` (long), `--coworker-id` (long), `--full-name`, `--email`, `--purchase-order`, `--checked-in` (bool), `--checked-in-date` (DateTime), `--from-checked-in-date` (range), `--to-checked-in-date` (range), `--invoiced` (bool), `--billed` (bool), `--created-on-local` (DateTime), `--from-created-on-local` (range), `--to-created-on-local` (range), `--checked-in-date-local` (DateTime), `--from-checked-in-date-local` (range), `--to-checked-in-date-local` (range), `--coworker-invoice-id` (int), `--from-coworker-invoice-id` (range), `--to-coworker-invoice-id` (range), `--coworker-invoice-number`, `--coworker-invoice-paid` (bool), `--reminded` (bool), `--zoom-event-data`, `--zoom-participant-id`, `--is-sent` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EventAttendee create options

`--business-id` (long, required), `--calendar-event-id` (long, required), `--event-product-id` (long, required), `--coworker-id` (long), `--full-name` (required), `--email` (required), `--purchase-order`, `--checked-in` (bool), `--checked-in-date` (DateTime), `--invoiced` (bool), `--billed` (bool), `--created-on-local` (DateTime), `--checked-in-date-local` (DateTime), `--coworker-invoice-id` (int), `--coworker-invoice-number`, `--coworker-invoice-paid` (bool), `--reminded` (bool), `--zoom-event-data`, `--zoom-participant-id`, `--is-sent` (bool)

#### EventAttendee update options

`--business-id` (long), `--calendar-event-id` (long), `--event-product-id` (long), `--coworker-id` (long), `--full-name`, `--email`, `--purchase-order`, `--checked-in` (bool), `--checked-in-date` (DateTime), `--billed` (bool), `--created-on-local` (DateTime), `--checked-in-date-local` (DateTime), `--coworker-invoice-id` (int), `--coworker-invoice-number`, `--coworker-invoice-paid` (bool), `--reminded` (bool), `--zoom-event-data`, `--zoom-participant-id`, `--is-sent` (bool)

<!-- END:GENERATED entity=EventAttendees -->
