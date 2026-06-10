# CoworkerBookingCreditUseHistories

<!-- BEGIN:GENERATED entity=CoworkerBookingCreditUseHistories -->

A **CoworkerBookingCreditUseHistory** records each time a `CoworkerBookingCredit` was consumed. Each entry captures the amount of credit deducted and links back to the booking, event attendance, or invoice line that triggered the use.

Use the read-only denormalised fields (`--booking-from-time`, `--booking-resource-name`, `--event-attendee-calendar-event-name`, etc.) to inspect what the credit was spent on without needing to fetch the related records separately.

CoworkerBookingCreditUseHistories support Search, Get, Create, Update (no Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkerbookingcreditusehistories list --agent` | List all coworkerbookingcreditusehistories |
| `nexudus coworkerbookingcreditusehistories list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerbookingcreditusehistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerbookingcreditusehistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerbookingcreditusehistories list --description <value> --coworker-booking-credit-id <value> --agent` | Filter coworkerbookingcreditusehistories by properties |
| `nexudus coworkerbookingcreditusehistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerbookingcreditusehistories list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerbookingcreditusehistories get <id> --agent` | Get single coworkerbookingcreditusehistory |
| `nexudus coworkerbookingcreditusehistories create --coworker-booking-credit-id <value> --credit-used <value> --agent` | Create coworkerbookingcreditusehistory |
| `nexudus coworkerbookingcreditusehistories update <id> --name "New Name" --agent` | Update coworkerbookingcreditusehistory |

#### CoworkerBookingCreditUseHistory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--description` | string | Optional description or note for this credit use entry |
| `--coworker-booking-credit-id` | long | ID of the booking credit that was consumed |
| `--booking-id` | long | ID of the booking this credit was applied to, if the credit was used for a booking |
| `--coworker-invoice-line-id` | long | ID of the invoice line this credit was applied to, if the credit was used against an invoice |
| `--event-attendee-id` | long | ID of the event attendance record this credit was applied to, if the credit was used for an event |
| `--credit-used` | decimal | Amount of credit consumed by this entry |
| `--from-credit-used` | range | |
| `--to-credit-used` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerBookingCreditUseHistory sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerBookingCreditUseHistory create options

| Option | Type | Description |
| --- | --- | --- |
| `--description` | string | Optional description or note for this credit use entry |
| `--coworker-booking-credit-id` | long, required | ID of the booking credit that was consumed |
| `--booking-id` | long | ID of the booking this credit was applied to, if the credit was used for a booking |
| `--coworker-invoice-line-id` | long | ID of the invoice line this credit was applied to, if the credit was used against an invoice |
| `--event-attendee-id` | long | ID of the event attendance record this credit was applied to, if the credit was used for an event |
| `--credit-used` | decimal, required | Amount of credit consumed by this entry |

#### CoworkerBookingCreditUseHistory update options

| Option | Type | Description |
| --- | --- | --- |
| `--description` | string | Optional description or note for this credit use entry |
| `--coworker-booking-credit-id` | long | ID of the booking credit that was consumed |
| `--booking-id` | long | ID of the booking this credit was applied to, if the credit was used for a booking |
| `--coworker-invoice-line-id` | long | ID of the invoice line this credit was applied to, if the credit was used against an invoice |
| `--event-attendee-id` | long | ID of the event attendance record this credit was applied to, if the credit was used for an event |

#### CoworkerBookingCreditUseHistory PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--event-attendee-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--event-attendee-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus coworkerbookingcreditusehistories update <id> --event-attendee-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerBookingCreditUseHistory (key fields)

`Id`, `BookingResourceName`, `CoworkerInvoiceLineCoworkerInvoiceInvoiceNumber`, `EventAttendeeCalendarEventName`

<!-- END:GENERATED entity=CoworkerBookingCreditUseHistories -->
