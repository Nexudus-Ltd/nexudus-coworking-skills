# EventAttendees

<!-- BEGIN:GENERATED entity=EventAttendees -->

An EventAttendee is an event ticket registration for a customer, linking the customer and ticket type to an event while tracking check-in, invoicing, and cancellation status.

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
| `--business-id` | long | ID of the location that owns this event registration. |
| `--calendar-event-id` | long | ID of the event this registration is for; it cannot be changed after creation. |
| `--calendar-event-name` | string | Display value for CalendarEvent.Name. |
| `--event-product-id` | long | ID of the ticket type purchased for the event; it cannot be changed after creation. |
| `--event-product-name` | string | Display value for EventProduct.Name. |
| `--event-product-price` | decimal | Display value for EventProduct.Price. |
| `--from-event-product-price` | range | |
| `--to-event-product-price` | range | |
| `--event-product-currency-code` | string | Display value for EventProduct.Currency.Code. |
| `--coworker-id` | long | Optional ID of the customer who purchased the ticket; a customer is created from the attendee name and email when none is supplied. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--full-name` | string | Full name of the person registered to attend; required. |
| `--email` | string | Email address of the person registered to attend; required. |
| `--purchase-order` | string | Optional purchase-order reference for this ticket registration. |
| `--attendee-code` | string | Read-only five-digit code generated for an unchecked-in attendee and used to find the registration at check-in. |
| `--checked-in` | bool | Whether the attendee has checked in to the event. |
| `--checked-in-date` | DateTime | Date and time in UTC when the attendee checked in; clear it when reversing a check-in. |
| `--from-checked-in-date` | range | |
| `--to-checked-in-date` | range | |
| `--invoiced` | bool | Whether this ticket registration is treated as invoiced when it is created; this value cannot be changed later. |
| `--due-date` | DateTime | Read-only payment due date associated with this ticket registration, when available. |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--coworker-invoice-id` | int | Read-only ID of the invoice containing this ticket registration, populated by the invoicing process. |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string | Read-only invoice number containing this ticket registration, populated by the invoicing process. |
| `--coworker-invoice-paid` | bool | Whether the associated invoice has been paid; read-only and populated by the invoicing process. |
| `--cancelled` | bool | Whether this ticket registration has been cancelled; cancelling an invoiced ticket can also cancel or refund its invoice through the cancellation workflow. |
| `--cancellation-reason` | enum | Reason for cancellation: Unknown, BadPreviousExperience, CantAttend, NoLongerNeeded, TooExpensive, or Other. |
| `--cancelled-on` | DateTime | Date and time in UTC when the ticket was cancelled, normally set by the cancellation workflow. |
| `--from-cancelled-on` | range | |
| `--to-cancelled-on` | range | |
| `--cancelled-by` | string | Name of the user or customer recorded as cancelling the ticket, normally set by the cancellation workflow. |
| `--cancellation-reason-details` | string | Optional cancellation explanation, limited to 255 characters; use it especially when CancellationReason is Other. |
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
| `--business-id` | long, required | ID of the location that owns this event registration. |
| `--calendar-event-id` | long, required | ID of the event this registration is for; it cannot be changed after creation. |
| `--event-product-id` | long, required | ID of the ticket type purchased for the event; it cannot be changed after creation. |
| `--coworker-id` | long | Optional ID of the customer who purchased the ticket; a customer is created from the attendee name and email when none is supplied. |
| `--full-name` | string, required | Full name of the person registered to attend; required. |
| `--email` | string, required | Email address of the person registered to attend; required. |
| `--purchase-order` | string | Optional purchase-order reference for this ticket registration. |
| `--checked-in` | bool | Whether the attendee has checked in to the event. |
| `--checked-in-date` | DateTime | Date and time in UTC when the attendee checked in; clear it when reversing a check-in. |
| `--invoiced` | bool | Whether this ticket registration is treated as invoiced when it is created; this value cannot be changed later. |
| `--cancelled` | bool | Whether this ticket registration has been cancelled; cancelling an invoiced ticket can also cancel or refund its invoice through the cancellation workflow. |
| `--cancellation-reason` | enum | Reason for cancellation: Unknown, BadPreviousExperience, CantAttend, NoLongerNeeded, TooExpensive, or Other. |
| `--cancelled-on` | DateTime | Date and time in UTC when the ticket was cancelled, normally set by the cancellation workflow. |
| `--cancelled-by` | string | Name of the user or customer recorded as cancelling the ticket, normally set by the cancellation workflow. |
| `--cancellation-reason-details` | string | Optional cancellation explanation, limited to 255 characters; use it especially when CancellationReason is Other. |

#### EventAttendee update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this event registration. |
| `--coworker-id` | long | Optional ID of the customer who purchased the ticket; a customer is created from the attendee name and email when none is supplied. |
| `--full-name` | string | Full name of the person registered to attend; required. |
| `--email` | string | Email address of the person registered to attend; required. |
| `--purchase-order` | string | Optional purchase-order reference for this ticket registration. |
| `--checked-in` | bool | Whether the attendee has checked in to the event. |
| `--checked-in-date` | DateTime | Date and time in UTC when the attendee checked in; clear it when reversing a check-in. |
| `--cancelled` | bool | Whether this ticket registration has been cancelled; cancelling an invoiced ticket can also cancel or refund its invoice through the cancellation workflow. |
| `--cancellation-reason` | enum | Reason for cancellation: Unknown, BadPreviousExperience, CantAttend, NoLongerNeeded, TooExpensive, or Other. |
| `--cancelled-on` | DateTime | Date and time in UTC when the ticket was cancelled, normally set by the cancellation workflow. |
| `--cancelled-by` | string | Name of the user or customer recorded as cancelling the ticket, normally set by the cancellation workflow. |
| `--cancellation-reason-details` | string | Optional cancellation explanation, limited to 255 characters; use it especially when CancellationReason is Other. |

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
