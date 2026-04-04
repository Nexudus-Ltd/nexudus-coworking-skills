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
| `nexudus cancelledbookings create --resource-id <value> --from-time <value> --to-time <value> --cancelled-on <value> --agent` | Create cancelledbooking |
| `nexudus cancelledbookings update <id> --name "New Name" --agent` | Update cancelledbooking |
| `nexudus cancelledbookings delete <id> --yes --agent` | Delete cancelledbooking (no prompt) |

#### CancelledBooking list filter options

`--resource-id`, `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time`, `--to-time`, `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--last-notification-time`, `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative`, `--online`, `--teams-at-the-time-of-booking`, `--tariff-at-the-time-of-booking`, `--repeat-series-unique-id`, `--repeat-booking`, `--repeats`, `--which-bookings-to-update`, `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--reminded`, `--mrm-reminded`, `--override-price`, `--invoiced`, `--invoice-date`, `--booking-number`, `--kisi-key-id`, `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed`, `--from-time-local`, `--to-time-local`, `--invoice-date-local`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--coworker-invoice-draft`, `--coworker-invoice-void`, `--coworker-invoice-credit-note`, `--coworker-extra-service-ids`, `--coworker-extra-service-price`, `--coworker-extra-service-currency-code`, `--coworker-extra-service-charge-period`, `--coworker-extra-service-total-uses`, `--include-zoom-invite`, `--zoom-event-data`, `--checked-in-at`, `--cancel-if-not-paid`, `--cancel-if-not-checked-in`, `--max-occupancy`, `--last-minute-price-adjustment`, `--dynamic-price-adjustment`, `--price-factor-last-minute`, `--price-factor-demand`, `--office365-admin-event-id`, `--cancellation-reason`, `--cancelled-on`, `--cancelled-by`, `--cancellation-reason-details`, `--price`, `--original-booking-id`

#### CancelledBooking create options

`--resource-id` (required), `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time` (required), `--to-time` (required), `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--last-notification-time`, `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative`, `--online`, `--teams-at-the-time-of-booking`, `--tariff-at-the-time-of-booking`, `--repeat-series-unique-id`, `--repeat-booking`, `--repeats`, `--which-bookings-to-update`, `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--reminded`, `--mrm-reminded`, `--override-price`, `--invoiced`, `--invoice-date`, `--booking-number`, `--kisi-key-id`, `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed`, `--from-time-local`, `--to-time-local`, `--invoice-date-local`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--coworker-invoice-draft`, `--coworker-invoice-void`, `--coworker-invoice-credit-note`, `--coworker-extra-service-ids`, `--coworker-extra-service-price`, `--coworker-extra-service-currency-code`, `--coworker-extra-service-charge-period`, `--coworker-extra-service-total-uses`, `--include-zoom-invite`, `--zoom-event-data`, `--checked-in-at`, `--cancel-if-not-paid`, `--cancel-if-not-checked-in`, `--max-occupancy`, `--last-minute-price-adjustment`, `--dynamic-price-adjustment`, `--price-factor-last-minute`, `--price-factor-demand`, `--office365-admin-event-id`, `--cancellation-reason`, `--cancelled-on` (required), `--cancelled-by`, `--cancellation-reason-details`, `--price`, `--original-booking-id`

#### CancelledBooking update options

`--start-scheduled-job-id`, `--cancellation-reason`, `--cancelled-on`, `--cancelled-by`

### CancelledBooking (key fields)

`Id`, `ResourceName`, `CoworkerFullName`, `FromTime`, `ToTime`, `CancellationReason`, `CancelledOn`

<!-- END:GENERATED entity=CancelledBookings -->
