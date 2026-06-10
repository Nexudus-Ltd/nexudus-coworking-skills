# EventAttendees

<!-- BEGIN:GENERATED entity=EventAttendees -->

An **EventAttendee** records a customer's registration for a calendar event. Each record links a customer to an event and tracks attendance details such as check-in status and whether the attendee was invoiced.

EventAttendees support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventattendees list --agent` | List all eventattendees |
| `nexudus eventattendees list --id <id> --agent` | Filter by single ID |
| `nexudus eventattendees list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventattendees list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventattendees list --business-id <value> --calendar-event-id <value> --agent` | Filter eventattendees by properties |
| `nexudus eventattendees list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventattendees list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus eventattendees get <id> --agent` | Get single eventattendee |
| `nexudus eventattendees create --business-id <value> --calendar-event-id <value> --event-product-id <value> --full-name <value> --email <value> --agent` | Create eventattendee |
| `nexudus eventattendees update <id> --name "New Name" --agent` | Update eventattendee |
| `nexudus eventattendees delete <id> --yes --agent` | Delete eventattendee (no prompt) |

#### EventAttendee list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--event-product-id` | long | ID of the event product linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--full-name` | string | The full name value for this event attendee |
| `--email` | string | The email value for this event attendee |
| `--purchase-order` | string | The purchase order value for this event attendee |
| `--checked-in` | bool | Whether checked in is enabled |
| `--checked-in-date` | DateTime | Date/time value for checked in date |
| `--from-checked-in-date` | range | |
| `--to-checked-in-date` | range | |
| `--invoiced` | bool | Whether invoiced is enabled |
| `--billed` | bool | Whether billed is enabled |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--from-created-on-local` | range | |
| `--to-created-on-local` | range | |
| `--checked-in-date-local` | DateTime | Date/time value for checked in date local |
| `--from-checked-in-date-local` | range | |
| `--to-checked-in-date-local` | range | |
| `--coworker-invoice-id` | int | ID of the coworker invoice associated with this record |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string | The coworker invoice number value for this event attendee |
| `--coworker-invoice-paid` | bool | Whether coworker invoice paid is enabled |
| `--reminded` | bool | Whether reminded is enabled |
| `--zoom-event-data` | string | The zoom event data value for this event attendee |
| `--zoom-participant-id` | string | ID of the zoom participant associated with this record |
| `--is-sent` | bool | Whether is sent is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EventAttendee sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EventAttendee create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--calendar-event-id` | long, required | ID of the calendar event linked to this record |
| `--event-product-id` | long, required | ID of the event product linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--full-name` | string, required | The full name value for this event attendee |
| `--email` | string, required | The email value for this event attendee |
| `--purchase-order` | string | The purchase order value for this event attendee |
| `--checked-in` | bool | Whether checked in is enabled |
| `--checked-in-date` | DateTime | Date/time value for checked in date |
| `--invoiced` | bool | Whether invoiced is enabled |
| `--billed` | bool | Whether billed is enabled |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--checked-in-date-local` | DateTime | Date/time value for checked in date local |
| `--coworker-invoice-id` | int | ID of the coworker invoice associated with this record |
| `--coworker-invoice-number` | string | The coworker invoice number value for this event attendee |
| `--coworker-invoice-paid` | bool | Whether coworker invoice paid is enabled |
| `--reminded` | bool | Whether reminded is enabled |
| `--zoom-event-data` | string | The zoom event data value for this event attendee |
| `--zoom-participant-id` | string | ID of the zoom participant associated with this record |
| `--is-sent` | bool | Whether is sent is enabled |

#### EventAttendee update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--event-product-id` | long | ID of the event product linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--full-name` | string | The full name value for this event attendee |
| `--email` | string | The email value for this event attendee |
| `--purchase-order` | string | The purchase order value for this event attendee |
| `--checked-in` | bool | Whether checked in is enabled |
| `--checked-in-date` | DateTime | Date/time value for checked in date |
| `--billed` | bool | Whether billed is enabled |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--checked-in-date-local` | DateTime | Date/time value for checked in date local |
| `--coworker-invoice-id` | int | ID of the coworker invoice associated with this record |
| `--coworker-invoice-number` | string | The coworker invoice number value for this event attendee |
| `--coworker-invoice-paid` | bool | Whether coworker invoice paid is enabled |
| `--reminded` | bool | Whether reminded is enabled |
| `--zoom-event-data` | string | The zoom event data value for this event attendee |
| `--zoom-participant-id` | string | ID of the zoom participant associated with this record |
| `--is-sent` | bool | Whether is sent is enabled |

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
