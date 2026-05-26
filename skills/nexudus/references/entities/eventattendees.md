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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--calendar-event-id` | long |  |
| `--event-product-id` | long |  |
| `--coworker-id` | long |  |
| `--full-name` | string |  |
| `--email` | string |  |
| `--purchase-order` | string |  |
| `--checked-in` | bool |  |
| `--checked-in-date` | DateTime |  |
| `--from-checked-in-date` | range | |
| `--to-checked-in-date` | range | |
| `--invoiced` | bool |  |
| `--billed` | bool |  |
| `--created-on-local` | DateTime |  |
| `--from-created-on-local` | range | |
| `--to-created-on-local` | range | |
| `--checked-in-date-local` | DateTime |  |
| `--from-checked-in-date-local` | range | |
| `--to-checked-in-date-local` | range | |
| `--coworker-invoice-id` | int |  |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string |  |
| `--coworker-invoice-paid` | bool |  |
| `--reminded` | bool |  |
| `--zoom-event-data` | string |  |
| `--zoom-participant-id` | string |  |
| `--is-sent` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EventAttendee create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--calendar-event-id` | long, required |  |
| `--event-product-id` | long, required |  |
| `--coworker-id` | long |  |
| `--full-name` | string, required |  |
| `--email` | string, required |  |
| `--purchase-order` | string |  |
| `--checked-in` | bool |  |
| `--checked-in-date` | DateTime |  |
| `--invoiced` | bool |  |
| `--billed` | bool |  |
| `--created-on-local` | DateTime |  |
| `--checked-in-date-local` | DateTime |  |
| `--coworker-invoice-id` | int |  |
| `--coworker-invoice-number` | string |  |
| `--coworker-invoice-paid` | bool |  |
| `--reminded` | bool |  |
| `--zoom-event-data` | string |  |
| `--zoom-participant-id` | string |  |
| `--is-sent` | bool |  |

#### EventAttendee update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--calendar-event-id` | long |  |
| `--event-product-id` | long |  |
| `--coworker-id` | long |  |
| `--full-name` | string |  |
| `--email` | string |  |
| `--purchase-order` | string |  |
| `--checked-in` | bool |  |
| `--checked-in-date` | DateTime |  |
| `--billed` | bool |  |
| `--created-on-local` | DateTime |  |
| `--checked-in-date-local` | DateTime |  |
| `--coworker-invoice-id` | int |  |
| `--coworker-invoice-number` | string |  |
| `--coworker-invoice-paid` | bool |  |
| `--reminded` | bool |  |
| `--zoom-event-data` | string |  |
| `--zoom-participant-id` | string |  |
| `--is-sent` | bool |  |

#### EventAttendee PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus eventattendees update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=EventAttendees -->
