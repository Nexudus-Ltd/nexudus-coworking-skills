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
| `--resource-id` | long | ID of the resource linked to this record |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--extra-service-id` | long | ID of the extra service linked to this record |
| `--from-time` | DateTime | Booking start time |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | Booking end time |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--notes` | string | Optional notes or comments about this cancelled booking |
| `--internal-notes` | string | The internal notes value for this cancelled booking |
| `--charge-now` | bool | Whether charge now is enabled |
| `--invoice-now` | bool | Whether invoice now is enabled |
| `--invoice-this-coworker` | bool | Whether invoice this coworker is enabled |
| `--do-not-use-booking-credit` | bool | Whether do not use booking credit is enabled |
| `--purchase-order` | string | The purchase order value for this cancelled booking |
| `--discount-code` | string | The discount code value for this cancelled booking |
| `--last-notification-time` | DateTime | Date/time value for last notification time |
| `--from-last-notification-time` | range | |
| `--to-last-notification-time` | range | |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--google-event-id` | string | ID of the google event associated with this record |
| `--office365-event-id` | string | ID of the office365 event associated with this record |
| `--public-google-event-id` | string | ID of the public google event associated with this record |
| `--tentative` | bool | Tentative booking. Must be approved by an administrator before confirmed or charged. Tentative bookings still block the calendar |
| `--online` | bool | Whether online is enabled |
| `--teams-at-the-time-of-booking` | string | The teams at the time of booking value for this cancelled booking |
| `--tariff-at-the-time-of-booking` | string | The tariff at the time of booking value for this cancelled booking |
| `--repeat-series-unique-id` | string | ID of the repeat series unique associated with this record |
| `--repeat-booking` | bool | Whether repeat booking is enabled |
| `--repeats` | enum | The repeats value for this cancelled booking |
| `--which-bookings-to-update` | enum | Date/time value for which bookings to update |
| `--repeat-every` | int | The repeat every value for this cancelled booking |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime | Date/time value for repeat until |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool | Whether repeat on mondays is enabled |
| `--repeat-on-tuesdays` | bool | Whether repeat on tuesdays is enabled |
| `--repeat-on-wednesdays` | bool | Whether repeat on wednesdays is enabled |
| `--repeat-on-thursdays` | bool | Whether repeat on thursdays is enabled |
| `--repeat-on-fridays` | bool | Whether repeat on fridays is enabled |
| `--repeat-on-saturdays` | bool | Whether repeat on saturdays is enabled |
| `--repeat-on-sundays` | bool | Whether repeat on sundays is enabled |
| `--reminded` | bool | Whether reminded is enabled |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |
| `--override-price` | decimal | The override price value for this cancelled booking |
| `--from-override-price` | range | |
| `--to-override-price` | range | |
| `--invoiced` | bool | Whether the booking had been charged. When true, a charge (CoworkerExtraService) had been posted to the customer account |
| `--invoice-date` | DateTime | Date/time value for invoice date |
| `--from-invoice-date` | range | |
| `--to-invoice-date` | range | |
| `--booking-number` | int | The booking number value for this cancelled booking |
| `--from-booking-number` | range | |
| `--to-booking-number` | range | |
| `--kisi-key-id` | int | ID of the kisi key associated with this record |
| `--from-kisi-key-id` | range | |
| `--to-kisi-key-id` | range | |
| `--start-scheduled-job-id` | string | ID of the start scheduled job associated with this record |
| `--end-scheduled-job-id` | string | ID of the end scheduled job associated with this record |
| `--billed` | bool | Whether billed is enabled |
| `--from-time-local` | DateTime | Date/time value for from time local |
| `--from-from-time-local` | range | |
| `--to-from-time-local` | range | |
| `--to-time-local` | DateTime | Date/time value for to time local |
| `--from-to-time-local` | range | |
| `--to-to-time-local` | range | |
| `--invoice-date-local` | DateTime | Date/time value for invoice date local |
| `--from-invoice-date-local` | range | |
| `--to-invoice-date-local` | range | |
| `--coworker-invoice-id` | int | ID of the coworker invoice associated with this record |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string | The coworker invoice number value for this cancelled booking |
| `--coworker-invoice-paid` | bool | Whether coworker invoice paid is enabled |
| `--coworker-invoice-draft` | bool | Whether coworker invoice draft is enabled |
| `--coworker-invoice-void` | bool | Whether coworker invoice void is enabled |
| `--coworker-invoice-credit-note` | bool | Whether coworker invoice credit note is enabled |
| `--coworker-extra-service-ids` | string | The coworker extra service ids value for this cancelled booking |
| `--coworker-extra-service-price` | decimal | The coworker extra service price value for this cancelled booking |
| `--from-coworker-extra-service-price` | range | |
| `--to-coworker-extra-service-price` | range | |
| `--coworker-extra-service-currency-code` | string | The coworker extra service currency code value for this cancelled booking |
| `--coworker-extra-service-charge-period` | int | The coworker extra service charge period value for this cancelled booking |
| `--from-coworker-extra-service-charge-period` | range | |
| `--to-coworker-extra-service-charge-period` | range | |
| `--coworker-extra-service-total-uses` | int | The coworker extra service total uses value for this cancelled booking |
| `--from-coworker-extra-service-total-uses` | range | |
| `--to-coworker-extra-service-total-uses` | range | |
| `--include-zoom-invite` | bool | Whether include zoom invite is enabled |
| `--zoom-event-data` | string | The zoom event data value for this cancelled booking |
| `--checked-in-at` | DateTime | Date/time value for checked in at |
| `--from-checked-in-at` | range | |
| `--to-checked-in-at` | range | |
| `--cancel-if-not-paid` | bool | Whether cancel if not paid is enabled |
| `--cancel-if-not-checked-in` | bool | Whether cancel if not checked in is enabled |
| `--max-occupancy` | int | The max occupancy value for this cancelled booking |
| `--from-max-occupancy` | range | |
| `--to-max-occupancy` | range | |
| `--last-minute-price-adjustment` | decimal | The last minute price adjustment value for this cancelled booking |
| `--from-last-minute-price-adjustment` | range | |
| `--to-last-minute-price-adjustment` | range | |
| `--dynamic-price-adjustment` | decimal | The dynamic price adjustment value for this cancelled booking |
| `--from-dynamic-price-adjustment` | range | |
| `--to-dynamic-price-adjustment` | range | |
| `--price-factor-last-minute` | decimal | The price factor last minute value for this cancelled booking |
| `--from-price-factor-last-minute` | range | |
| `--to-price-factor-last-minute` | range | |
| `--price-factor-demand` | decimal | The price factor demand value for this cancelled booking |
| `--from-price-factor-demand` | range | |
| `--to-price-factor-demand` | range | |
| `--office365-admin-event-id` | string | ID of the office365 admin event associated with this record |
| `--cancellation-reason` | enum | Reason the booking was cancelled, e.g. NoLongerNeeded, TooExpensive, or NotCheckedIn |
| `--cancelled-on` | DateTime | Date and time when the booking was cancelled |
| `--from-cancelled-on` | range | |
| `--to-cancelled-on` | range | |
| `--cancelled-by` | string | Name or identifier of the user who cancelled the booking |
| `--cancellation-reason-details` | string | Additional free-text details explaining the cancellation reason |
| `--price` | decimal | Booking price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--original-booking-id` | string | ID of the original booking associated with this record |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CancelledBooking create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the resource linked to this record |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--extra-service-id` | long | ID of the extra service linked to this record |
| `--from-time` | DateTime, required | Booking start time |
| `--to-time` | DateTime, required | Booking end time |
| `--notes` | string | Optional notes or comments about this cancelled booking |
| `--internal-notes` | string | The internal notes value for this cancelled booking |
| `--charge-now` | bool | Whether charge now is enabled |
| `--invoice-now` | bool | Whether invoice now is enabled |
| `--invoice-this-coworker` | bool | Whether invoice this coworker is enabled |
| `--do-not-use-booking-credit` | bool | Whether do not use booking credit is enabled |
| `--purchase-order` | string | The purchase order value for this cancelled booking |
| `--discount-code` | string | The discount code value for this cancelled booking |
| `--last-notification-time` | DateTime | Date/time value for last notification time |
| `--google-calendar-id` | string | ID of the google calendar associated with this record |
| `--google-event-id` | string | ID of the google event associated with this record |
| `--office365-event-id` | string | ID of the office365 event associated with this record |
| `--public-google-event-id` | string | ID of the public google event associated with this record |
| `--tentative` | bool | Tentative booking. Must be approved by an administrator before confirmed or charged. Tentative bookings still block the calendar |
| `--online` | bool | Whether online is enabled |
| `--teams-at-the-time-of-booking` | string | The teams at the time of booking value for this cancelled booking |
| `--tariff-at-the-time-of-booking` | string | The tariff at the time of booking value for this cancelled booking |
| `--repeat-series-unique-id` | string | ID of the repeat series unique associated with this record |
| `--repeat-booking` | bool | Whether repeat booking is enabled |
| `--repeats` | enum, required | The repeats value for this cancelled booking |
| `--which-bookings-to-update` | enum, required | Date/time value for which bookings to update |
| `--repeat-every` | int | The repeat every value for this cancelled booking |
| `--repeat-until` | DateTime | Date/time value for repeat until |
| `--repeat-on-mondays` | bool | Whether repeat on mondays is enabled |
| `--repeat-on-tuesdays` | bool | Whether repeat on tuesdays is enabled |
| `--repeat-on-wednesdays` | bool | Whether repeat on wednesdays is enabled |
| `--repeat-on-thursdays` | bool | Whether repeat on thursdays is enabled |
| `--repeat-on-fridays` | bool | Whether repeat on fridays is enabled |
| `--repeat-on-saturdays` | bool | Whether repeat on saturdays is enabled |
| `--repeat-on-sundays` | bool | Whether repeat on sundays is enabled |
| `--reminded` | bool | Whether reminded is enabled |
| `--mrm-reminded` | bool | Whether mrm reminded is enabled |
| `--override-price` | decimal | The override price value for this cancelled booking |
| `--invoiced` | bool | Whether the booking had been charged. When true, a charge (CoworkerExtraService) had been posted to the customer account |
| `--invoice-date` | DateTime | Date/time value for invoice date |
| `--booking-number` | int | The booking number value for this cancelled booking |
| `--kisi-key-id` | int | ID of the kisi key associated with this record |
| `--start-scheduled-job-id` | string | ID of the start scheduled job associated with this record |
| `--end-scheduled-job-id` | string | ID of the end scheduled job associated with this record |
| `--billed` | bool | Whether billed is enabled |
| `--from-time-local` | DateTime | Date/time value for from time local |
| `--to-time-local` | DateTime | Date/time value for to time local |
| `--invoice-date-local` | DateTime | Date/time value for invoice date local |
| `--coworker-invoice-id` | int | ID of the coworker invoice associated with this record |
| `--coworker-invoice-number` | string | The coworker invoice number value for this cancelled booking |
| `--coworker-invoice-paid` | bool | Whether coworker invoice paid is enabled |
| `--coworker-invoice-draft` | bool | Whether coworker invoice draft is enabled |
| `--coworker-invoice-void` | bool | Whether coworker invoice void is enabled |
| `--coworker-invoice-credit-note` | bool | Whether coworker invoice credit note is enabled |
| `--coworker-extra-service-ids` | string | The coworker extra service ids value for this cancelled booking |
| `--coworker-extra-service-price` | decimal | The coworker extra service price value for this cancelled booking |
| `--coworker-extra-service-currency-code` | string | The coworker extra service currency code value for this cancelled booking |
| `--coworker-extra-service-charge-period` | int | The coworker extra service charge period value for this cancelled booking |
| `--coworker-extra-service-total-uses` | int | The coworker extra service total uses value for this cancelled booking |
| `--include-zoom-invite` | bool | Whether include zoom invite is enabled |
| `--zoom-event-data` | string | The zoom event data value for this cancelled booking |
| `--checked-in-at` | DateTime | Date/time value for checked in at |
| `--cancel-if-not-paid` | bool | Whether cancel if not paid is enabled |
| `--cancel-if-not-checked-in` | bool | Whether cancel if not checked in is enabled |
| `--max-occupancy` | int | The max occupancy value for this cancelled booking |
| `--last-minute-price-adjustment` | decimal | The last minute price adjustment value for this cancelled booking |
| `--dynamic-price-adjustment` | decimal | The dynamic price adjustment value for this cancelled booking |
| `--price-factor-last-minute` | decimal | The price factor last minute value for this cancelled booking |
| `--price-factor-demand` | decimal | The price factor demand value for this cancelled booking |
| `--office365-admin-event-id` | string | ID of the office365 admin event associated with this record |
| `--cancellation-reason` | enum | Reason the booking was cancelled, e.g. NoLongerNeeded, TooExpensive, or NotCheckedIn |
| `--cancelled-on` | DateTime, required | Date and time when the booking was cancelled |
| `--cancelled-by` | string | Name or identifier of the user who cancelled the booking |
| `--cancellation-reason-details` | string | Additional free-text details explaining the cancellation reason |
| `--price` | decimal | Booking price |
| `--original-booking-id` | string | ID of the original booking associated with this record |

#### CancelledBooking update options

| Option | Type | Description |
| --- | --- | --- |
| `--start-scheduled-job-id` | string | ID of the start scheduled job associated with this record |
| `--cancellation-reason` | enum | Reason the booking was cancelled, e.g. NoLongerNeeded, TooExpensive, or NotCheckedIn |
| `--cancelled-on` | DateTime | Date and time when the booking was cancelled |
| `--cancelled-by` | string | Name or identifier of the user who cancelled the booking |

#### CancelledBooking PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus cancelledbookings update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CancelledBooking (key fields)

`Id`, `ResourceName`, `CoworkerFullName`, `FromTime`, `ToTime`, `CancellationReason`, `CancelledOn`

#### CancelledBooking enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeats` | `1` Daily, `2` Weekly, `3` Monthly, `4` Yearly, `5` FirstOfMonth, `6` SecondOfMonth, `7` ThirdOfMonth, `8` LastOfMonth, `9` FourthOfMonth |
| `--which-bookings-to-update` | `1` UpdateThisBookingOnly, `2` UpdateFutureBookingsOnly, `3` UpdateAllBookings, `4` UpdateNotChargedBookings, `5` DeleteAllBookings, `6` DeleteBookingsAfterThis, `7` DeleteNotChargedBookings, `8` RevertAllCharges |

<!-- END:GENERATED entity=CancelledBookings -->
