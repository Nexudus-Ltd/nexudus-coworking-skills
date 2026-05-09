# CancelledBookings

<!-- BEGIN:GENERATED entity=CancelledBookings -->

A **CancelledBooking** is a read-only snapshot of a booking that was removed from the calendar. When a booking is cancelled, the system preserves its details — resource, coworker, time range, price, and cancellation metadata — so they remain available for reporting and auditing.

Cancelled bookings cannot be created or modified through the API; they are generated automatically when an active `Booking` is cancelled. Use `list` and `get` to query cancellation history.

The `CancellationReason` field indicates why the booking was removed. Possible reasons include the customer no longer needing the booking, cost concerns, rebooking for a different time, failure to pay upfront, automated cancellation due to not checking in, and others.

CancelledBookings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus cancelledbookings list --agent` | List all cancelledbookings |
| `nexudus cancelledbookings list --id <id> --agent` | Filter by single ID |
| `nexudus cancelledbookings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus cancelledbookings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus cancelledbookings list --from-time <value> --to-time <value> --agent` | Filter cancelledbookings by properties |
| `nexudus cancelledbookings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus cancelledbookings get <id> --agent` | Get single cancelledbooking |
| `nexudus cancelledbookings create --resource-id <value> --from-time <value> --to-time <value> --repeats <value> --which-bookings-to-update <value> --cancelled-on <value> --agent` | Create cancelledbooking |
| `nexudus cancelledbookings update <id> --name "New Name" --agent` | Update cancelledbooking |
| `nexudus cancelledbookings delete <id> --yes --agent` | Delete cancelledbooking (no prompt) |

#### CancelledBooking list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long |  |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--extra-service-id` | long |  |
| `--from-time` | DateTime | Booking start time |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | Booking end time |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--notes` | string | Notes |
| `--internal-notes` | string |  |
| `--charge-now` | bool |  |
| `--invoice-now` | bool |  |
| `--invoice-this-coworker` | bool |  |
| `--do-not-use-booking-credit` | bool |  |
| `--purchase-order` | string |  |
| `--discount-code` | string |  |
| `--last-notification-time` | DateTime |  |
| `--from-last-notification-time` | range | |
| `--to-last-notification-time` | range | |
| `--google-calendar-id` | string |  |
| `--google-event-id` | string |  |
| `--office365-event-id` | string |  |
| `--public-google-event-id` | string |  |
| `--tentative` | bool | Tentative booking. Must be approved by an administrator before confirmed or charged. Tentative bookings still block the calendar |
| `--online` | bool |  |
| `--teams-at-the-time-of-booking` | string |  |
| `--tariff-at-the-time-of-booking` | string |  |
| `--repeat-series-unique-id` | string |  |
| `--repeat-booking` | bool |  |
| `--repeats` | enum |  |
| `--which-bookings-to-update` | enum |  |
| `--repeat-every` | int |  |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime |  |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool |  |
| `--repeat-on-tuesdays` | bool |  |
| `--repeat-on-wednesdays` | bool |  |
| `--repeat-on-thursdays` | bool |  |
| `--repeat-on-fridays` | bool |  |
| `--repeat-on-saturdays` | bool |  |
| `--repeat-on-sundays` | bool |  |
| `--reminded` | bool |  |
| `--mrm-reminded` | bool |  |
| `--override-price` | decimal |  |
| `--from-override-price` | range | |
| `--to-override-price` | range | |
| `--invoiced` | bool | Whether the booking had been charged. When true, a charge (CoworkerExtraService) had been posted to the customer account |
| `--invoice-date` | DateTime |  |
| `--from-invoice-date` | range | |
| `--to-invoice-date` | range | |
| `--booking-number` | int |  |
| `--from-booking-number` | range | |
| `--to-booking-number` | range | |
| `--kisi-key-id` | int |  |
| `--from-kisi-key-id` | range | |
| `--to-kisi-key-id` | range | |
| `--start-scheduled-job-id` | string |  |
| `--end-scheduled-job-id` | string |  |
| `--billed` | bool |  |
| `--from-time-local` | DateTime |  |
| `--from-from-time-local` | range | |
| `--to-from-time-local` | range | |
| `--to-time-local` | DateTime |  |
| `--from-to-time-local` | range | |
| `--to-to-time-local` | range | |
| `--invoice-date-local` | DateTime |  |
| `--from-invoice-date-local` | range | |
| `--to-invoice-date-local` | range | |
| `--coworker-invoice-id` | int |  |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string |  |
| `--coworker-invoice-paid` | bool |  |
| `--coworker-invoice-draft` | bool |  |
| `--coworker-invoice-void` | bool |  |
| `--coworker-invoice-credit-note` | bool |  |
| `--coworker-extra-service-ids` | string |  |
| `--coworker-extra-service-price` | decimal |  |
| `--from-coworker-extra-service-price` | range | |
| `--to-coworker-extra-service-price` | range | |
| `--coworker-extra-service-currency-code` | string |  |
| `--coworker-extra-service-charge-period` | int |  |
| `--from-coworker-extra-service-charge-period` | range | |
| `--to-coworker-extra-service-charge-period` | range | |
| `--coworker-extra-service-total-uses` | int |  |
| `--from-coworker-extra-service-total-uses` | range | |
| `--to-coworker-extra-service-total-uses` | range | |
| `--include-zoom-invite` | bool |  |
| `--zoom-event-data` | string |  |
| `--checked-in-at` | DateTime |  |
| `--from-checked-in-at` | range | |
| `--to-checked-in-at` | range | |
| `--cancel-if-not-paid` | bool |  |
| `--cancel-if-not-checked-in` | bool |  |
| `--max-occupancy` | int |  |
| `--from-max-occupancy` | range | |
| `--to-max-occupancy` | range | |
| `--last-minute-price-adjustment` | decimal |  |
| `--from-last-minute-price-adjustment` | range | |
| `--to-last-minute-price-adjustment` | range | |
| `--dynamic-price-adjustment` | decimal |  |
| `--from-dynamic-price-adjustment` | range | |
| `--to-dynamic-price-adjustment` | range | |
| `--price-factor-last-minute` | decimal |  |
| `--from-price-factor-last-minute` | range | |
| `--to-price-factor-last-minute` | range | |
| `--price-factor-demand` | decimal |  |
| `--from-price-factor-demand` | range | |
| `--to-price-factor-demand` | range | |
| `--office365-admin-event-id` | string |  |
| `--cancellation-reason` | enum | Reason the booking was cancelled, e.g. NoLongerNeeded, TooExpensive, or NotCheckedIn |
| `--cancelled-on` | DateTime | Date and time when the booking was cancelled |
| `--from-cancelled-on` | range | |
| `--to-cancelled-on` | range | |
| `--cancelled-by` | string | Name or identifier of the user who cancelled the booking |
| `--cancellation-reason-details` | string | Additional free-text details explaining the cancellation reason |
| `--price` | decimal | Booking price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--original-booking-id` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CancelledBooking create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required |  |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--extra-service-id` | long |  |
| `--from-time` | DateTime, required | Booking start time |
| `--to-time` | DateTime, required | Booking end time |
| `--notes` | string | Notes |
| `--internal-notes` | string |  |
| `--charge-now` | bool |  |
| `--invoice-now` | bool |  |
| `--invoice-this-coworker` | bool |  |
| `--do-not-use-booking-credit` | bool |  |
| `--purchase-order` | string |  |
| `--discount-code` | string |  |
| `--last-notification-time` | DateTime |  |
| `--google-calendar-id` | string |  |
| `--google-event-id` | string |  |
| `--office365-event-id` | string |  |
| `--public-google-event-id` | string |  |
| `--tentative` | bool | Tentative booking. Must be approved by an administrator before confirmed or charged. Tentative bookings still block the calendar |
| `--online` | bool |  |
| `--teams-at-the-time-of-booking` | string |  |
| `--tariff-at-the-time-of-booking` | string |  |
| `--repeat-series-unique-id` | string |  |
| `--repeat-booking` | bool |  |
| `--repeats` | enum, required |  |
| `--which-bookings-to-update` | enum, required |  |
| `--repeat-every` | int |  |
| `--repeat-until` | DateTime |  |
| `--repeat-on-mondays` | bool |  |
| `--repeat-on-tuesdays` | bool |  |
| `--repeat-on-wednesdays` | bool |  |
| `--repeat-on-thursdays` | bool |  |
| `--repeat-on-fridays` | bool |  |
| `--repeat-on-saturdays` | bool |  |
| `--repeat-on-sundays` | bool |  |
| `--reminded` | bool |  |
| `--mrm-reminded` | bool |  |
| `--override-price` | decimal |  |
| `--invoiced` | bool | Whether the booking had been charged. When true, a charge (CoworkerExtraService) had been posted to the customer account |
| `--invoice-date` | DateTime |  |
| `--booking-number` | int |  |
| `--kisi-key-id` | int |  |
| `--start-scheduled-job-id` | string |  |
| `--end-scheduled-job-id` | string |  |
| `--billed` | bool |  |
| `--from-time-local` | DateTime |  |
| `--to-time-local` | DateTime |  |
| `--invoice-date-local` | DateTime |  |
| `--coworker-invoice-id` | int |  |
| `--coworker-invoice-number` | string |  |
| `--coworker-invoice-paid` | bool |  |
| `--coworker-invoice-draft` | bool |  |
| `--coworker-invoice-void` | bool |  |
| `--coworker-invoice-credit-note` | bool |  |
| `--coworker-extra-service-ids` | string |  |
| `--coworker-extra-service-price` | decimal |  |
| `--coworker-extra-service-currency-code` | string |  |
| `--coworker-extra-service-charge-period` | int |  |
| `--coworker-extra-service-total-uses` | int |  |
| `--include-zoom-invite` | bool |  |
| `--zoom-event-data` | string |  |
| `--checked-in-at` | DateTime |  |
| `--cancel-if-not-paid` | bool |  |
| `--cancel-if-not-checked-in` | bool |  |
| `--max-occupancy` | int |  |
| `--last-minute-price-adjustment` | decimal |  |
| `--dynamic-price-adjustment` | decimal |  |
| `--price-factor-last-minute` | decimal |  |
| `--price-factor-demand` | decimal |  |
| `--office365-admin-event-id` | string |  |
| `--cancellation-reason` | enum | Reason the booking was cancelled, e.g. NoLongerNeeded, TooExpensive, or NotCheckedIn |
| `--cancelled-on` | DateTime, required | Date and time when the booking was cancelled |
| `--cancelled-by` | string | Name or identifier of the user who cancelled the booking |
| `--cancellation-reason-details` | string | Additional free-text details explaining the cancellation reason |
| `--price` | decimal | Booking price |
| `--original-booking-id` | string |  |

#### CancelledBooking update options

| Option | Type | Description |
| --- | --- | --- |
| `--start-scheduled-job-id` | string |  |
| `--cancellation-reason` | enum | Reason the booking was cancelled, e.g. NoLongerNeeded, TooExpensive, or NotCheckedIn |
| `--cancelled-on` | DateTime | Date and time when the booking was cancelled |
| `--cancelled-by` | string | Name or identifier of the user who cancelled the booking |

### CancelledBooking (key fields)

`Id`, `ResourceName`, `CoworkerFullName`, `FromTime`, `ToTime`, `CancellationReason`, `CancelledOn`

<!-- END:GENERATED entity=CancelledBookings -->
