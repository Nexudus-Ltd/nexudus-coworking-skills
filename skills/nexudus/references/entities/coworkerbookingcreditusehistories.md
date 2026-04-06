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
| `nexudus coworkerbookingcreditusehistories get <id> --agent` | Get single coworkerbookingcreditusehistory |
| `nexudus coworkerbookingcreditusehistories create --coworker-booking-credit-id <value> --credit-used <value> --agent` | Create coworkerbookingcreditusehistory |
| `nexudus coworkerbookingcreditusehistories update <id> --name "New Name" --agent` | Update coworkerbookingcreditusehistory |

#### CoworkerBookingCreditUseHistory list filter options

`--description`, `--coworker-booking-credit-id`, `--booking-id`, `--coworker-invoice-line-id`, `--event-attendee-id`, `--credit-used`, `--from-credit-used` (range), `--to-credit-used` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerBookingCreditUseHistory create options

`--description`, `--coworker-booking-credit-id` (required), `--booking-id`, `--coworker-invoice-line-id`, `--event-attendee-id`, `--credit-used` (required)

#### CoworkerBookingCreditUseHistory update options

`--description`, `--coworker-booking-credit-id`, `--booking-id`, `--coworker-invoice-line-id`, `--event-attendee-id`

### CoworkerBookingCreditUseHistory (key fields)

`Id`, `BookingResourceName`, `CoworkerInvoiceLineCoworkerInvoiceInvoiceNumber`, `EventAttendeeCalendarEventName`

<!-- END:GENERATED entity=CoworkerBookingCreditUseHistories -->
