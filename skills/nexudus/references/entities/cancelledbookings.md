# CancelledBookings

<!-- BEGIN:GENERATED entity=CancelledBookings -->

A cancelled booking is the audit snapshot created when a resource reservation is cancelled, preserving its resource, customer, time, price, and cancellation reason for reporting.

CancelledBookings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus cancelledbookings list --agent` | List all cancelledbookings |
| `nexudus cancelledbookings list --id <id> --agent` | Filter by single ID |
| `nexudus cancelledbookings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus cancelledbookings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus cancelledbookings list --from-time <value> --to-time <value> --agent` | Filter cancelledbookings by properties |
| `nexudus cancelledbookings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus cancelledbookings list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus cancelledbookings get <id> --agent` | Get single cancelledbooking |
| `nexudus cancelledbookings create --resource-id <value> --from-time <value> --to-time <value> --repeats <value> --which-bookings-to-update <value> --cancelled-on <value> --agent` | Create cancelledbooking |
| `nexudus cancelledbookings update <id> --name "New Name" --agent` | Update cancelledbooking |
| `nexudus cancelledbookings delete <id> --yes --agent` | Delete cancelledbooking (no prompt) |

#### CancelledBooking list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource that was reserved; it determines the cancelled booking's location. |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the resource when the booking was cancelled. |
| `--coworker-id` | long | Optional ID of the customer whose booking was cancelled. |
| `--extra-service-id` | long | Optional ID of the booking rate used when the cancelled booking was priced. |
| `--from-time` | DateTime | UTC date and time when the cancelled booking began. |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | UTC date and time when the cancelled booking ended; it is after FromTime. |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--notes` | string | Customer-facing notes retained from the cancelled booking. |
| `--internal-notes` | string | Internal staff notes retained from the cancelled booking. |
| `--charge-now` | bool | Whether the original booking was requested to be charged immediately. |
| `--invoice-now` | bool | Whether the original booking was requested to generate an invoice immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer was the billing party for the original booking. |
| `--do-not-use-booking-credit` | bool | Whether customer booking credit was prevented from being used for the original booking. |
| `--purchase-order` | string | Customer purchase-order reference retained from the cancelled booking. |
| `--discount-code` | string | Discount code retained from the cancelled booking. |
| `--last-notification-time` | DateTime | Internal UTC timestamp maintained for the last booking notification. |
| `--from-last-notification-time` | range | |
| `--to-last-notification-time` | range | |
| `--google-calendar-id` | string | Internal Google Calendar identifier maintained by calendar synchronization. |
| `--google-event-id` | string | Internal Google Calendar event identifier maintained by calendar synchronization. |
| `--office365-event-id` | string | Internal Microsoft 365 calendar event identifier maintained by synchronization. |
| `--public-google-event-id` | string | Internal public Google Calendar event identifier maintained by synchronization. |
| `--tentative` | bool | Whether the cancelled booking was tentative and awaiting confirmation; tentative bookings still blocked the calendar. |
| `--online` | bool | Whether the cancelled booking was for an online resource. |
| `--teams-at-the-time-of-booking` | string | System snapshot of the customer's team memberships when the cancelled booking was made. |
| `--tariff-at-the-time-of-booking` | string | System snapshot of the customer's plan when the cancelled booking was made. |
| `--repeat-series-unique-id` | string | System-generated identifier linking bookings from the same recurrence series. |
| `--repeat-booking` | bool | Whether the cancelled booking was created as part of a recurrence series. |
| `--repeats` | enum | Recurrence cycle retained from the booking: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-bookings-to-update` | enum | Original recurrence action: UpdateThisBookingOnly, UpdateFutureBookingsOnly, UpdateAllBookings, UpdateNotChargedBookings, DeleteAllBookings, DeleteBookingsAfterThis, DeleteNotChargedBookings, or RevertAllCharges. |
| `--repeat-every` | int | Recurrence interval retained from the booking; for example, 2 with Weekly means every two weeks. |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime | Final UTC date and time for creating occurrences in the original recurrence series. |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool | Whether the original weekly recurrence included Mondays. |
| `--repeat-on-tuesdays` | bool | Whether the original weekly recurrence included Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether the original weekly recurrence included Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether the original weekly recurrence included Thursdays. |
| `--repeat-on-fridays` | bool | Whether the original weekly recurrence included Fridays. |
| `--repeat-on-saturdays` | bool | Whether the original weekly recurrence included Saturdays. |
| `--repeat-on-sundays` | bool | Whether the original weekly recurrence included Sundays. |
| `--reminded` | bool | System flag showing whether the standard booking reminder had been sent. |
| `--mrm-reminded` | bool | System flag showing whether an MRM reminder had been sent. |
| `--override-price` | decimal | Optional total price override retained from the original booking, before normal rate calculation. |
| `--from-override-price` | range | |
| `--to-override-price` | range | |
| `--invoiced` | bool | Whether a charge was posted to the customer account for the original booking; it does not indicate invoice status. |
| `--invoice-date` | DateTime | UTC date and time when the original booking was charged. |
| `--from-invoice-date` | range | |
| `--to-invoice-date` | range | |
| `--booking-number` | int | System-generated reference number retained from the original booking. |
| `--from-booking-number` | range | |
| `--to-booking-number` | range | |
| `--kisi-key-id` | int | Internal Kisi access-control key identifier retained from the original booking. |
| `--from-kisi-key-id` | range | |
| `--to-kisi-key-id` | range | |
| `--start-scheduled-job-id` | string | Internal scheduled-job identifier for the original booking start. |
| `--end-scheduled-job-id` | string | Internal scheduled-job identifier for the original booking end. |
| `--billed` | bool | Internal billing-processing state retained from the original booking. |
| `--from-time-local` | DateTime | System-maintained local-time representation of FromTime. |
| `--from-from-time-local` | range | |
| `--to-from-time-local` | range | |
| `--to-time-local` | DateTime | System-maintained local-time representation of ToTime. |
| `--from-to-time-local` | range | |
| `--to-to-time-local` | range | |
| `--invoice-date-local` | DateTime | System-maintained local-time representation of InvoiceDate. |
| `--from-invoice-date-local` | range | |
| `--to-invoice-date-local` | range | |
| `--coworker-invoice-id` | int | ID of the invoice associated with the original booking; manage it through the invoice entity. |
| `--from-coworker-invoice-id` | range | |
| `--to-coworker-invoice-id` | range | |
| `--coworker-invoice-number` | string | Invoice number associated with the original booking, when it was included in an invoice. |
| `--coworker-invoice-paid` | bool | Whether the invoice associated with the original booking has been paid. |
| `--coworker-invoice-draft` | bool | Whether the invoice associated with the original booking is a draft. |
| `--coworker-invoice-void` | bool | Whether the invoice associated with the original booking has been voided. |
| `--coworker-invoice-credit-note` | bool | Whether the invoice associated with the original booking is a credit note. |
| `--coworker-extra-service-ids` | string | Internal serialized identifiers of customer rate entitlements used by the original booking. |
| `--coworker-extra-service-price` | decimal | System-calculated price from the customer's applicable booking rate entitlement. |
| `--from-coworker-extra-service-price` | range | |
| `--to-coworker-extra-service-price` | range | |
| `--coworker-extra-service-currency-code` | string | System-calculated currency code for the customer rate entitlement used by the original booking. |
| `--coworker-extra-service-charge-period` | int | System-calculated charge-period setting for the customer rate entitlement used by the original booking. |
| `--from-coworker-extra-service-charge-period` | range | |
| `--to-coworker-extra-service-charge-period` | range | |
| `--coworker-extra-service-total-uses` | int | System-calculated number of customer rate uses consumed or available for the original booking. |
| `--from-coworker-extra-service-total-uses` | range | |
| `--to-coworker-extra-service-total-uses` | range | |
| `--include-zoom-invite` | bool | Whether the original booking included a Zoom meeting invitation. |
| `--zoom-event-data` | string | Internal Zoom event payload maintained by the integration. |
| `--checked-in-at` | DateTime | UTC date and time when the original booking was checked in through the booking workflow. |
| `--from-checked-in-at` | range | |
| `--to-checked-in-at` | range | |
| `--cancel-if-not-paid` | bool | Whether the resource policy cancelled the booking when payment was not received. |
| `--cancel-if-not-checked-in` | bool | Whether the resource policy cancelled the booking when no check-in occurred. |
| `--max-occupancy` | int | Maximum occupancy detected by sensors in the resource during the original booking. |
| `--from-max-occupancy` | range | |
| `--to-max-occupancy` | range | |
| `--last-minute-price-adjustment` | decimal | System-calculated monetary dynamic-pricing adjustment applied for a last-minute booking. |
| `--from-last-minute-price-adjustment` | range | |
| `--to-last-minute-price-adjustment` | range | |
| `--dynamic-price-adjustment` | decimal | System-calculated monetary adjustment from dynamic-pricing settings for the resource or location. |
| `--from-dynamic-price-adjustment` | range | |
| `--to-dynamic-price-adjustment` | range | |
| `--price-factor-last-minute` | decimal | System-calculated multiplier used for the last-minute dynamic-pricing adjustment. |
| `--from-price-factor-last-minute` | range | |
| `--to-price-factor-last-minute` | range | |
| `--price-factor-demand` | decimal | System-calculated multiplier used for demand-based dynamic pricing. |
| `--from-price-factor-demand` | range | |
| `--to-price-factor-demand` | range | |
| `--office365-admin-event-id` | string | Internal Microsoft 365 administrator calendar event identifier maintained by synchronization. |
| `--cancellation-reason` | enum | Reason the booking was cancelled: Unknown, NoLongerNeeded, TooExpensive, BadPreviousExperience, RebookedForADifferentTime, FailedToPayUpfront, Integration, Other, NotCheckedIn, or MarketPlace. |
| `--cancelled-on` | DateTime | UTC date and time when the booking was cancelled. |
| `--from-cancelled-on` | range | |
| `--to-cancelled-on` | range | |
| `--cancelled-by` | string | Name or identifier supplied by the user or process that cancelled the booking. |
| `--cancellation-reason-details` | string | Optional free-text details explaining the cancellation reason, up to 255 characters. |
| `--price` | decimal | Final calculated price of the booking at cancellation, including the system's booking cost calculation. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--original-booking-id` | string | GUID of the original booking from which this cancellation record was created. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CancelledBooking sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `FromTime` ascending. If no `--order-by` is specified, the API returns results ordered by `FromTime` (ascending).

#### CancelledBooking create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the resource that was reserved; it determines the cancelled booking's location. |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the resource when the booking was cancelled. |
| `--coworker-id` | long | Optional ID of the customer whose booking was cancelled. |
| `--extra-service-id` | long | Optional ID of the booking rate used when the cancelled booking was priced. |
| `--from-time` | DateTime, required | UTC date and time when the cancelled booking began. |
| `--to-time` | DateTime, required | UTC date and time when the cancelled booking ended; it is after FromTime. |
| `--notes` | string | Customer-facing notes retained from the cancelled booking. |
| `--internal-notes` | string | Internal staff notes retained from the cancelled booking. |
| `--charge-now` | bool | Whether the original booking was requested to be charged immediately. |
| `--invoice-now` | bool | Whether the original booking was requested to generate an invoice immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer was the billing party for the original booking. |
| `--do-not-use-booking-credit` | bool | Whether customer booking credit was prevented from being used for the original booking. |
| `--purchase-order` | string | Customer purchase-order reference retained from the cancelled booking. |
| `--discount-code` | string | Discount code retained from the cancelled booking. |
| `--last-notification-time` | DateTime | Internal UTC timestamp maintained for the last booking notification. |
| `--google-calendar-id` | string | Internal Google Calendar identifier maintained by calendar synchronization. |
| `--google-event-id` | string | Internal Google Calendar event identifier maintained by calendar synchronization. |
| `--office365-event-id` | string | Internal Microsoft 365 calendar event identifier maintained by synchronization. |
| `--public-google-event-id` | string | Internal public Google Calendar event identifier maintained by synchronization. |
| `--tentative` | bool | Whether the cancelled booking was tentative and awaiting confirmation; tentative bookings still blocked the calendar. |
| `--online` | bool | Whether the cancelled booking was for an online resource. |
| `--teams-at-the-time-of-booking` | string | System snapshot of the customer's team memberships when the cancelled booking was made. |
| `--tariff-at-the-time-of-booking` | string | System snapshot of the customer's plan when the cancelled booking was made. |
| `--repeat-series-unique-id` | string | System-generated identifier linking bookings from the same recurrence series. |
| `--repeat-booking` | bool | Whether the cancelled booking was created as part of a recurrence series. |
| `--repeats` | enum, required | Recurrence cycle retained from the booking: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-bookings-to-update` | enum, required | Original recurrence action: UpdateThisBookingOnly, UpdateFutureBookingsOnly, UpdateAllBookings, UpdateNotChargedBookings, DeleteAllBookings, DeleteBookingsAfterThis, DeleteNotChargedBookings, or RevertAllCharges. |
| `--repeat-every` | int | Recurrence interval retained from the booking; for example, 2 with Weekly means every two weeks. |
| `--repeat-until` | DateTime | Final UTC date and time for creating occurrences in the original recurrence series. |
| `--repeat-on-mondays` | bool | Whether the original weekly recurrence included Mondays. |
| `--repeat-on-tuesdays` | bool | Whether the original weekly recurrence included Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether the original weekly recurrence included Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether the original weekly recurrence included Thursdays. |
| `--repeat-on-fridays` | bool | Whether the original weekly recurrence included Fridays. |
| `--repeat-on-saturdays` | bool | Whether the original weekly recurrence included Saturdays. |
| `--repeat-on-sundays` | bool | Whether the original weekly recurrence included Sundays. |
| `--reminded` | bool | System flag showing whether the standard booking reminder had been sent. |
| `--mrm-reminded` | bool | System flag showing whether an MRM reminder had been sent. |
| `--override-price` | decimal | Optional total price override retained from the original booking, before normal rate calculation. |
| `--invoiced` | bool | Whether a charge was posted to the customer account for the original booking; it does not indicate invoice status. |
| `--invoice-date` | DateTime | UTC date and time when the original booking was charged. |
| `--booking-number` | int | System-generated reference number retained from the original booking. |
| `--kisi-key-id` | int | Internal Kisi access-control key identifier retained from the original booking. |
| `--start-scheduled-job-id` | string | Internal scheduled-job identifier for the original booking start. |
| `--end-scheduled-job-id` | string | Internal scheduled-job identifier for the original booking end. |
| `--billed` | bool | Internal billing-processing state retained from the original booking. |
| `--from-time-local` | DateTime | System-maintained local-time representation of FromTime. |
| `--to-time-local` | DateTime | System-maintained local-time representation of ToTime. |
| `--invoice-date-local` | DateTime | System-maintained local-time representation of InvoiceDate. |
| `--coworker-invoice-id` | int | ID of the invoice associated with the original booking; manage it through the invoice entity. |
| `--coworker-invoice-number` | string | Invoice number associated with the original booking, when it was included in an invoice. |
| `--coworker-invoice-paid` | bool | Whether the invoice associated with the original booking has been paid. |
| `--coworker-invoice-draft` | bool | Whether the invoice associated with the original booking is a draft. |
| `--coworker-invoice-void` | bool | Whether the invoice associated with the original booking has been voided. |
| `--coworker-invoice-credit-note` | bool | Whether the invoice associated with the original booking is a credit note. |
| `--coworker-extra-service-ids` | string | Internal serialized identifiers of customer rate entitlements used by the original booking. |
| `--coworker-extra-service-price` | decimal | System-calculated price from the customer's applicable booking rate entitlement. |
| `--coworker-extra-service-currency-code` | string | System-calculated currency code for the customer rate entitlement used by the original booking. |
| `--coworker-extra-service-charge-period` | int | System-calculated charge-period setting for the customer rate entitlement used by the original booking. |
| `--coworker-extra-service-total-uses` | int | System-calculated number of customer rate uses consumed or available for the original booking. |
| `--include-zoom-invite` | bool | Whether the original booking included a Zoom meeting invitation. |
| `--zoom-event-data` | string | Internal Zoom event payload maintained by the integration. |
| `--checked-in-at` | DateTime | UTC date and time when the original booking was checked in through the booking workflow. |
| `--cancel-if-not-paid` | bool | Whether the resource policy cancelled the booking when payment was not received. |
| `--cancel-if-not-checked-in` | bool | Whether the resource policy cancelled the booking when no check-in occurred. |
| `--max-occupancy` | int | Maximum occupancy detected by sensors in the resource during the original booking. |
| `--last-minute-price-adjustment` | decimal | System-calculated monetary dynamic-pricing adjustment applied for a last-minute booking. |
| `--dynamic-price-adjustment` | decimal | System-calculated monetary adjustment from dynamic-pricing settings for the resource or location. |
| `--price-factor-last-minute` | decimal | System-calculated multiplier used for the last-minute dynamic-pricing adjustment. |
| `--price-factor-demand` | decimal | System-calculated multiplier used for demand-based dynamic pricing. |
| `--office365-admin-event-id` | string | Internal Microsoft 365 administrator calendar event identifier maintained by synchronization. |
| `--cancellation-reason` | enum | Reason the booking was cancelled: Unknown, NoLongerNeeded, TooExpensive, BadPreviousExperience, RebookedForADifferentTime, FailedToPayUpfront, Integration, Other, NotCheckedIn, or MarketPlace. |
| `--cancelled-on` | DateTime, required | UTC date and time when the booking was cancelled. |
| `--cancelled-by` | string | Name or identifier supplied by the user or process that cancelled the booking. |
| `--cancellation-reason-details` | string | Optional free-text details explaining the cancellation reason, up to 255 characters. |
| `--price` | decimal | Final calculated price of the booking at cancellation, including the system's booking cost calculation. |
| `--original-booking-id` | string | GUID of the original booking from which this cancellation record was created. |

#### CancelledBooking update options

| Option | Type | Description |
| --- | --- | --- |
| `--start-scheduled-job-id` | string | Internal scheduled-job identifier for the original booking start. |
| `--cancellation-reason` | enum | Reason the booking was cancelled: Unknown, NoLongerNeeded, TooExpensive, BadPreviousExperience, RebookedForADifferentTime, FailedToPayUpfront, Integration, Other, NotCheckedIn, or MarketPlace. |
| `--cancelled-on` | DateTime | UTC date and time when the booking was cancelled. |
| `--cancelled-by` | string | Name or identifier supplied by the user or process that cancelled the booking. |

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
