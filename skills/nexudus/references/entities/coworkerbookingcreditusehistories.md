# CoworkerBookingCreditUseHistories

<!-- BEGIN:GENERATED entity=CoworkerBookingCreditUseHistories -->

A read-only ledger entry for a customer booking credit (monetary credit). The system writes one entry each time credit is spent on a booking, an event ticket or an invoice, and each time an admin adjusts the balance. creditUsed is the amount deducted; a negative amount is credit given back by a manual adjustment. bookingId, eventAttendeeId and the description say what the credit paid for, and the denormalised fields (bookingResourceName, bookingFromTime, eventAttendeeCalendarEventName, ...) save fetching those records. Filter by coworkerBookingCredit_id for one credit, or by coworker_id / coworker_id_in for a customer's or a team's usage across all their credits. To add or remove credit, run ADJUST_BOOKING_CREDIT on the booking credit; entries cannot be created or edited here.

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
| `--coworker-booking-credit-coworker-full-name` | string | Display value for CoworkerBookingCredit.Coworker.FullName. |
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
| `--coworker-booking-credit-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--event-attendee-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--event-attendee-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus coworkerbookingcreditusehistories update <id> --coworker-booking-credit-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerBookingCreditUseHistory (key fields)

`Id`, `BookingResourceName`, `CoworkerInvoiceLineCoworkerInvoiceInvoiceNumber`, `EventAttendeeCalendarEventName`

<!-- END:GENERATED entity=CoworkerBookingCreditUseHistories -->
