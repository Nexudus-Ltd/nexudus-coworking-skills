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

`--resource-id`, `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time`, `--from-from-time` (range), `--to-from-time` (range), `--to-time`, `--from-to-time` (range), `--to-to-time` (range), `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--last-notification-time`, `--from-last-notification-time` (range), `--to-last-notification-time` (range), `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative`, `--online`, `--teams-at-the-time-of-booking`, `--tariff-at-the-time-of-booking`, `--repeat-series-unique-id`, `--repeat-booking`, `--repeats`, `--which-bookings-to-update`, `--repeat-every`, `--from-repeat-every` (range), `--to-repeat-every` (range), `--repeat-until`, `--from-repeat-until` (range), `--to-repeat-until` (range), `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--reminded`, `--mrm-reminded`, `--override-price`, `--from-override-price` (range), `--to-override-price` (range), `--invoiced`, `--invoice-date`, `--from-invoice-date` (range), `--to-invoice-date` (range), `--booking-number`, `--from-booking-number` (range), `--to-booking-number` (range), `--kisi-key-id`, `--from-kisi-key-id` (range), `--to-kisi-key-id` (range), `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed`, `--from-time-local`, `--from-from-time-local` (range), `--to-from-time-local` (range), `--to-time-local`, `--from-to-time-local` (range), `--to-to-time-local` (range), `--invoice-date-local`, `--from-invoice-date-local` (range), `--to-invoice-date-local` (range), `--coworker-invoice-id`, `--from-coworker-invoice-id` (range), `--to-coworker-invoice-id` (range), `--coworker-invoice-number`, `--coworker-invoice-paid`, `--coworker-invoice-draft`, `--coworker-invoice-void`, `--coworker-invoice-credit-note`, `--coworker-extra-service-ids`, `--coworker-extra-service-price`, `--from-coworker-extra-service-price` (range), `--to-coworker-extra-service-price` (range), `--coworker-extra-service-currency-code`, `--coworker-extra-service-charge-period`, `--from-coworker-extra-service-charge-period` (range), `--to-coworker-extra-service-charge-period` (range), `--coworker-extra-service-total-uses`, `--from-coworker-extra-service-total-uses` (range), `--to-coworker-extra-service-total-uses` (range), `--include-zoom-invite`, `--zoom-event-data`, `--checked-in-at`, `--from-checked-in-at` (range), `--to-checked-in-at` (range), `--cancel-if-not-paid`, `--cancel-if-not-checked-in`, `--max-occupancy`, `--from-max-occupancy` (range), `--to-max-occupancy` (range), `--last-minute-price-adjustment`, `--from-last-minute-price-adjustment` (range), `--to-last-minute-price-adjustment` (range), `--dynamic-price-adjustment`, `--from-dynamic-price-adjustment` (range), `--to-dynamic-price-adjustment` (range), `--price-factor-last-minute`, `--from-price-factor-last-minute` (range), `--to-price-factor-last-minute` (range), `--price-factor-demand`, `--from-price-factor-demand` (range), `--to-price-factor-demand` (range), `--office365-admin-event-id`, `--cancellation-reason`, `--cancelled-on`, `--from-cancelled-on` (range), `--to-cancelled-on` (range), `--cancelled-by`, `--cancellation-reason-details`, `--price`, `--from-price` (range), `--to-price` (range), `--original-booking-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CancelledBooking create options

`--resource-id` (required), `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time` (required), `--to-time` (required), `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--last-notification-time`, `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative`, `--online`, `--teams-at-the-time-of-booking`, `--tariff-at-the-time-of-booking`, `--repeat-series-unique-id`, `--repeat-booking`, `--repeats` (required), `--which-bookings-to-update` (required), `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--reminded`, `--mrm-reminded`, `--override-price`, `--invoiced`, `--invoice-date`, `--booking-number`, `--kisi-key-id`, `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed`, `--from-time-local`, `--to-time-local`, `--invoice-date-local`, `--coworker-invoice-id`, `--coworker-invoice-number`, `--coworker-invoice-paid`, `--coworker-invoice-draft`, `--coworker-invoice-void`, `--coworker-invoice-credit-note`, `--coworker-extra-service-ids`, `--coworker-extra-service-price`, `--coworker-extra-service-currency-code`, `--coworker-extra-service-charge-period`, `--coworker-extra-service-total-uses`, `--include-zoom-invite`, `--zoom-event-data`, `--checked-in-at`, `--cancel-if-not-paid`, `--cancel-if-not-checked-in`, `--max-occupancy`, `--last-minute-price-adjustment`, `--dynamic-price-adjustment`, `--price-factor-last-minute`, `--price-factor-demand`, `--office365-admin-event-id`, `--cancellation-reason`, `--cancelled-on` (required), `--cancelled-by`, `--cancellation-reason-details`, `--price`, `--original-booking-id`

#### CancelledBooking update options

`--start-scheduled-job-id`, `--cancellation-reason`, `--cancelled-on`, `--cancelled-by`

### CancelledBooking (key fields)

`Id`, `ResourceName`, `CoworkerFullName`, `FromTime`, `ToTime`, `CancellationReason`, `CancelledOn`

<!-- END:GENERATED entity=CancelledBookings -->
