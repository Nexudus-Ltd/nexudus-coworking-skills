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
| `nexudus coworkerbookingcreditusehistories list --booking-resource-name <value> --coworker-invoice-line-coworker-invoice-invoice-number <value> --agent` | Filter coworkerbookingcreditusehistories by properties |
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
| `--coworker-booking-credit-business-currency-code` | string | Display value for CoworkerBookingCredit.Business.Currency.Code. |
| `--coworker-booking-credit-coworker-id` | int | Display value for CoworkerBookingCredit.Coworker.Id. |
| `--from-coworker-booking-credit-coworker-id` | range | |
| `--to-coworker-booking-credit-coworker-id` | range | |
| `--coworker-booking-credit-description` | string | Display value for CoworkerBookingCredit.Description. |
| `--coworker-booking-credit-tariff-booking-credit-name` | string | Display value for CoworkerBookingCredit.TariffBookingCredit.Name. |
| `--coworker-booking-credit-expire-date` | DateTime | Display value for CoworkerBookingCredit.ExpireDate. |
| `--from-coworker-booking-credit-expire-date` | range | |
| `--to-coworker-booking-credit-expire-date` | range | |
| `--coworker-booking-credit-remaining-credit` | decimal | Display value for CoworkerBookingCredit.RemainingCredit. |
| `--from-coworker-booking-credit-remaining-credit` | range | |
| `--to-coworker-booking-credit-remaining-credit` | range | |
| `--coworker-booking-credit-coworker-product-unique-id` | string | Display value for CoworkerBookingCredit.CoworkerProductUniqueId. |
| `--booking-id` | long | ID of the booking this credit was applied to, if the credit was used for a booking |
| `--booking-from-time` | DateTime | Display value for Booking.FromTime. |
| `--from-booking-from-time` | range | |
| `--to-booking-from-time` | range | |
| `--booking-to-time` | DateTime | Display value for Booking.ToTime. |
| `--from-booking-to-time` | range | |
| `--to-booking-to-time` | range | |
| `--booking-resource-name` | string | Display value for Booking.Resource.Name. |
| `--coworker-invoice-line-id` | long | ID of the invoice line this credit was applied to, if the credit was used against an invoice |
| `--coworker-invoice-line-coworker-invoice-id` | int | Display value for CoworkerInvoiceLine.CoworkerInvoice.Id. |
| `--from-coworker-invoice-line-coworker-invoice-id` | range | |
| `--to-coworker-invoice-line-coworker-invoice-id` | range | |
| `--coworker-invoice-line-coworker-invoice-invoice-number` | string | Display value for CoworkerInvoiceLine.CoworkerInvoice.InvoiceNumber. |
| `--event-attendee-id` | long | ID of the event attendance record this credit was applied to, if the credit was used for an event |
| `--event-attendee-calendar-event-name` | string | Display value for EventAttendee.CalendarEvent.Name. |
| `--event-attendee-event-product-name` | string | Display value for EventAttendee.EventProduct.Name. |
| `--event-attendee-full-name` | string | Display value for EventAttendee.FullName. |
| `--event-attendee-email` | string | Display value for EventAttendee.Email. |
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
