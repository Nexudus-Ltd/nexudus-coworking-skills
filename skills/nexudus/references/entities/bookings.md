# Bookings

<!-- BEGIN:GENERATED entity=Bookings -->

A booking is a reservation of a resource, such as a meeting room or desk, for a customer at a specified time; it can be tentative, recurring, charged, and invoiced.

Bookings support Search, Get, Create, Update, Delete.
Bookings also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus bookings list --agent` | List all bookings |
| `nexudus bookings list --id <id> --agent` | Filter by single ID |
| `nexudus bookings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus bookings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus bookings list --from-time <value> --to-time <value> --agent` | Filter bookings by properties |
| `nexudus bookings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus bookings list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus bookings get <id> --agent` | Get single booking |
| `nexudus bookings create --resource-id <value> --from-time <value> --to-time <value> --repeats <value> --which-bookings-to-update <value> --agent` | Create booking |
| `nexudus bookings update <id> --name "New Name" --agent` | Update booking |
| `nexudus bookings delete <id> --yes --agent` | Delete booking (no prompt) |
| `nexudus bookings run-command <key> <ids> --agent` | Run entity command |

#### Booking list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource being reserved; it determines the booking location and availability rules. |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the selected resource. The unit must be connected to this resource |
| `--coworker-id` | long | Optional ID of the customer this booking is for. |
| `--extra-service-id` | long | Optional ID of the rate used to price this booking. Set it only to a rate linked to the selected resource's ResourceType. When no rate is provided, the system calculates an applicable rate automatically. |
| `--from-time` | DateTime | Booking start date and time in UTC. |
| `--from-from-time` | range | |
| `--to-from-time` | range | |
| `--to-time` | DateTime | Booking end date and time in UTC; it must be after FromTime. |
| `--from-to-time` | range | |
| `--to-to-time` | range | |
| `--notes` | string | Customer-facing notes for the booking. |
| `--internal-notes` | string | Internal staff notes recorded when the booking is created. |
| `--charge-now` | bool | Whether to charge the booking immediately when it is created or updated. |
| `--invoice-now` | bool | Whether to generate an invoice for the booking immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer receives the booking charge. When false, the customer's team-paying member, if any, is the billing party. |
| `--do-not-use-booking-credit` | bool | Whether to prevent available customer booking credit from being used for this booking. |
| `--purchase-order` | string | Optional customer purchase-order reference for the booking. |
| `--discount-code` | string | Optional discount code applied when the booking price is calculated. |
| `--last-notification-time` | DateTime | System-maintained UTC timestamp of the last booking notification. |
| `--from-last-notification-time` | range | |
| `--to-last-notification-time` | range | |
| `--google-calendar-id` | string | Internal Google Calendar identifier maintained by calendar synchronization. |
| `--google-event-id` | string | Internal Google Calendar event identifier maintained by calendar synchronization. |
| `--office365-event-id` | string | Internal Microsoft 365 calendar event identifier maintained by synchronization. |
| `--public-google-event-id` | string | Internal public Google Calendar event identifier maintained by synchronization. |
| `--tentative` | bool | Whether the booking is tentative and still requires confirmation. Customer bookings for resources requiring confirmation are created as tentative; administrators can create tentative bookings for any resource. |
| `--teams-at-booking` | string | System snapshot of the customer's team memberships when the booking was made. |
| `--tariff-at-booking` | string | System snapshot of the customer's plan when the booking was made. |
| `--repeat-series-unique-id` | string | System-generated identifier linking all bookings in the same recurrence series; use it to find and update all bookings in that series. |
| `--repeat-booking` | bool | Whether to create a recurring series from this booking. |
| `--repeats` | enum | Recurrence cycle: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-bookings-to-update` | enum | For a recurring booking update, selects whether to update this booking, future bookings, all bookings, not-charged bookings, or perform the corresponding delete or charge-reversal action. |
| `--repeat-every` | int | Optional positive recurrence interval; for example, 2 with Weekly repeats every two weeks. |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime | Optional final UTC date and time for creating occurrences in the recurrence series. |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool | Whether a weekly recurring booking includes Mondays. |
| `--repeat-on-tuesdays` | bool | Whether a weekly recurring booking includes Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether a weekly recurring booking includes Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether a weekly recurring booking includes Thursdays. |
| `--repeat-on-fridays` | bool | Whether a weekly recurring booking includes Fridays. |
| `--repeat-on-saturdays` | bool | Whether a weekly recurring booking includes Saturdays. |
| `--repeat-on-sundays` | bool | Whether a weekly recurring booking includes Sundays. |
| `--reminded` | bool | System flag showing whether the standard booking reminder has been sent. |
| `--mrm-reminded` | bool | System flag showing whether an MRM reminder has been sent. |
| `--override-price` | decimal | Optional total price override for this booking, before normal rate calculation. |
| `--from-override-price` | range | |
| `--to-override-price` | range | |
| `--kisi-key-id` | int | Internal Kisi access-control key identifier for this booking. |
| `--from-kisi-key-id` | range | |
| `--to-kisi-key-id` | range | |
| `--start-scheduled-job-id` | string | Internal scheduled-job identifier for the booking start. |
| `--end-scheduled-job-id` | string | Internal scheduled-job identifier for the booking end. |
| `--billed` | bool | Internal billing-processing state for this booking. |
| `--from-time-local` | DateTime | System-maintained local-time representation of FromTime. |
| `--from-from-time-local` | range | |
| `--to-from-time-local` | range | |
| `--to-time-local` | DateTime | System-maintained local-time representation of ToTime. |
| `--from-to-time-local` | range | |
| `--to-to-time-local` | range | |
| `--invoice-date-local` | DateTime | System-maintained local-time representation of InvoiceDate. |
| `--from-invoice-date-local` | range | |
| `--to-invoice-date-local` | range | |
| `--coworker-extra-service-price` | decimal | System-calculated price from the customer's applicable rate entitlement. |
| `--from-coworker-extra-service-price` | range | |
| `--to-coworker-extra-service-price` | range | |
| `--include-zoom-invite` | bool | Whether to include a Zoom meeting invitation for this booking. |
| `--zoom-event-data` | string | Internal Zoom event payload maintained by the integration. |
| `--office365-admin-event-id` | string | Internal Microsoft 365 administrator calendar event identifier maintained by synchronization. |
| `--coworker-checked-in-at` | DateTime | UTC date and time when the customer checked in for this booking. |
| `--from-coworker-checked-in-at` | range | |
| `--to-coworker-checked-in-at` | range | |
| `--coworker-checked-out-at` | DateTime | UTC date and time when the customer checked out from this booking. |
| `--from-coworker-checked-out-at` | range | |
| `--to-coworker-checked-out-at` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Booking sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `FromTime` ascending. If no `--order-by` is specified, the API returns results ordered by `FromTime` (ascending).

#### Booking create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the resource being reserved; it determines the booking location and availability rules. |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the selected resource. The unit must be connected to this resource |
| `--coworker-id` | long | Optional ID of the customer this booking is for. |
| `--extra-service-id` | long | Optional ID of the rate used to price this booking. Set it only to a rate linked to the selected resource's ResourceType. When no rate is provided, the system calculates an applicable rate automatically. |
| `--from-time` | DateTime, required | Booking start date and time in UTC. |
| `--to-time` | DateTime, required | Booking end date and time in UTC; it must be after FromTime. |
| `--notes` | string | Customer-facing notes for the booking. |
| `--internal-notes` | string | Internal staff notes recorded when the booking is created. |
| `--charge-now` | bool | Whether to charge the booking immediately when it is created or updated. |
| `--invoice-now` | bool | Whether to generate an invoice for the booking immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer receives the booking charge. When false, the customer's team-paying member, if any, is the billing party. |
| `--do-not-use-booking-credit` | bool | Whether to prevent available customer booking credit from being used for this booking. |
| `--purchase-order` | string | Optional customer purchase-order reference for the booking. |
| `--discount-code` | string | Optional discount code applied when the booking price is calculated. |
| `--last-notification-time` | DateTime | System-maintained UTC timestamp of the last booking notification. |
| `--google-calendar-id` | string | Internal Google Calendar identifier maintained by calendar synchronization. |
| `--google-event-id` | string | Internal Google Calendar event identifier maintained by calendar synchronization. |
| `--office365-event-id` | string | Internal Microsoft 365 calendar event identifier maintained by synchronization. |
| `--public-google-event-id` | string | Internal public Google Calendar event identifier maintained by synchronization. |
| `--tentative` | bool | Whether the booking is tentative and still requires confirmation. Customer bookings for resources requiring confirmation are created as tentative; administrators can create tentative bookings for any resource. |
| `--teams-at-booking` | string | System snapshot of the customer's team memberships when the booking was made. |
| `--tariff-at-booking` | string | System snapshot of the customer's plan when the booking was made. |
| `--repeat-series-unique-id` | string | System-generated identifier linking all bookings in the same recurrence series; use it to find and update all bookings in that series. |
| `--repeat-booking` | bool | Whether to create a recurring series from this booking. |
| `--repeats` | enum, required | Recurrence cycle: Daily, Weekly, Monthly, Yearly, FirstOfMonth, SecondOfMonth, ThirdOfMonth, FourthOfMonth, or LastOfMonth. |
| `--which-bookings-to-update` | enum, required | For a recurring booking update, selects whether to update this booking, future bookings, all bookings, not-charged bookings, or perform the corresponding delete or charge-reversal action. |
| `--repeat-every` | int | Optional positive recurrence interval; for example, 2 with Weekly repeats every two weeks. |
| `--repeat-until` | DateTime | Optional final UTC date and time for creating occurrences in the recurrence series. |
| `--repeat-on-mondays` | bool | Whether a weekly recurring booking includes Mondays. |
| `--repeat-on-tuesdays` | bool | Whether a weekly recurring booking includes Tuesdays. |
| `--repeat-on-wednesdays` | bool | Whether a weekly recurring booking includes Wednesdays. |
| `--repeat-on-thursdays` | bool | Whether a weekly recurring booking includes Thursdays. |
| `--repeat-on-fridays` | bool | Whether a weekly recurring booking includes Fridays. |
| `--repeat-on-saturdays` | bool | Whether a weekly recurring booking includes Saturdays. |
| `--repeat-on-sundays` | bool | Whether a weekly recurring booking includes Sundays. |
| `--reminded` | bool | System flag showing whether the standard booking reminder has been sent. |
| `--mrm-reminded` | bool | System flag showing whether an MRM reminder has been sent. |
| `--override-price` | decimal | Optional total price override for this booking, before normal rate calculation. |
| `--kisi-key-id` | int | Internal Kisi access-control key identifier for this booking. |
| `--start-scheduled-job-id` | string | Internal scheduled-job identifier for the booking start. |
| `--end-scheduled-job-id` | string | Internal scheduled-job identifier for the booking end. |
| `--billed` | bool | Internal billing-processing state for this booking. |
| `--from-time-local` | DateTime | System-maintained local-time representation of FromTime. |
| `--to-time-local` | DateTime | System-maintained local-time representation of ToTime. |
| `--invoice-date-local` | DateTime | System-maintained local-time representation of InvoiceDate. |
| `--coworker-extra-service-price` | decimal | System-calculated price from the customer's applicable rate entitlement. |
| `--include-zoom-invite` | bool | Whether to include a Zoom meeting invitation for this booking. |
| `--zoom-event-data` | string | Internal Zoom event payload maintained by the integration. |
| `--office365-admin-event-id` | string | Internal Microsoft 365 administrator calendar event identifier maintained by synchronization. |
| `--coworker-checked-in-at` | DateTime | UTC date and time when the customer checked in for this booking. |
| `--coworker-checked-out-at` | DateTime | UTC date and time when the customer checked out from this booking. |
| `--booking-products` | JSON array or @filepath | Products to include with this booking |
| `--booking-visitors` | JSON array or @filepath | Visitors to add to this booking |

#### Booking update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource being reserved; it determines the booking location and availability rules. |
| `--floor-plan-desk-id` | long | Optional ID of the floor-plan unit assigned within the selected resource. The unit must be connected to this resource |
| `--coworker-id` | long | Optional ID of the customer this booking is for. |
| `--extra-service-id` | long | Optional ID of the rate used to price this booking. Set it only to a rate linked to the selected resource's ResourceType. When no rate is provided, the system calculates an applicable rate automatically. |
| `--from-time` | DateTime | Booking start date and time in UTC. |
| `--to-time` | DateTime | Booking end date and time in UTC; it must be after FromTime. |
| `--notes` | string | Customer-facing notes for the booking. |
| `--charge-now` | bool | Whether to charge the booking immediately when it is created or updated. |
| `--invoice-now` | bool | Whether to generate an invoice for the booking immediately. |
| `--invoice-this-coworker` | bool | Whether the selected customer receives the booking charge. When false, the customer's team-paying member, if any, is the billing party. |
| `--do-not-use-booking-credit` | bool | Whether to prevent available customer booking credit from being used for this booking. |
| `--purchase-order` | string | Optional customer purchase-order reference for the booking. |
| `--discount-code` | string | Optional discount code applied when the booking price is calculated. |
| `--last-notification-time` | DateTime | System-maintained UTC timestamp of the last booking notification. |
| `--google-calendar-id` | string | Internal Google Calendar identifier maintained by calendar synchronization. |
| `--google-event-id` | string | Internal Google Calendar event identifier maintained by calendar synchronization. |
| `--office365-event-id` | string | Internal Microsoft 365 calendar event identifier maintained by synchronization. |
| `--public-google-event-id` | string | Internal public Google Calendar event identifier maintained by synchronization. |
| `--tentative` | bool | Whether the booking is tentative and still requires confirmation. Customer bookings for resources requiring confirmation are created as tentative; administrators can create tentative bookings for any resource. |
| `--teams-at-booking` | string | System snapshot of the customer's team memberships when the booking was made. |
| `--tariff-at-booking` | string | System snapshot of the customer's plan when the booking was made. |
| `--which-bookings-to-update` | enum | For a recurring booking update, selects whether to update this booking, future bookings, all bookings, not-charged bookings, or perform the corresponding delete or charge-reversal action. |
| `--reminded` | bool | System flag showing whether the standard booking reminder has been sent. |
| `--mrm-reminded` | bool | System flag showing whether an MRM reminder has been sent. |
| `--override-price` | decimal | Optional total price override for this booking, before normal rate calculation. |
| `--kisi-key-id` | int | Internal Kisi access-control key identifier for this booking. |
| `--start-scheduled-job-id` | string | Internal scheduled-job identifier for the booking start. |
| `--end-scheduled-job-id` | string | Internal scheduled-job identifier for the booking end. |
| `--billed` | bool | Internal billing-processing state for this booking. |
| `--from-time-local` | DateTime | System-maintained local-time representation of FromTime. |
| `--to-time-local` | DateTime | System-maintained local-time representation of ToTime. |
| `--invoice-date-local` | DateTime | System-maintained local-time representation of InvoiceDate. |
| `--coworker-extra-service-price` | decimal | System-calculated price from the customer's applicable rate entitlement. |
| `--include-zoom-invite` | bool | Whether to include a Zoom meeting invitation for this booking. |
| `--zoom-event-data` | string | Internal Zoom event payload maintained by the integration. |
| `--office365-admin-event-id` | string | Internal Microsoft 365 administrator calendar event identifier maintained by synchronization. |
| `--coworker-checked-in-at` | DateTime | UTC date and time when the customer checked in for this booking. |
| `--coworker-checked-out-at` | DateTime | UTC date and time when the customer checked out from this booking. |
| `--booking-products` | JSON array or @filepath | Products to include with this booking |
| `--booking-visitors` | JSON array or @filepath | Visitors to add to this booking |

#### Booking PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-mobile-phone` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--coworker-land-line` | `PHONE` | `«PII:PHONE:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus bookings update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### Booking (key fields)

`Id`, `ResourceName`, `CoworkerFullName`, `FromTime`, `ToTime`, `Tentative`, `Invoiced`

#### Booking inline children

Booking supports inline child objects on create and update. Pass a JSON array or a `@filepath` reference.

**`--booking-products`** — Products to include with this booking

Writable properties: `ProductId`, `Quantity`, `InvoiceInMinutes`

```shell
nexudus bookings create ... --booking-products '[{"ProductId": 123, "Quantity": 123, "InvoiceInMinutes": true}]' --agent
```

Or from a file:

```shell
nexudus bookings create ... --booking-products @bookingproducts.json --agent
```

**`--booking-visitors`** — Visitors to add to this booking

Writable properties: `VisitorFullName`, `VisitorEmail`

```shell
nexudus bookings create ... --booking-visitors '[{"VisitorFullName": "...", "VisitorEmail": "..."}]' --agent
```

Or from a file:

```shell
nexudus bookings create ... --booking-visitors @bookingvisitors.json --agent
```

#### Booking enum values

| Option | Valid values |
| ------ | ------------ |
| `--repeats` | `1` Daily, `2` Weekly, `3` Monthly, `4` Yearly, `5` FirstOfMonth, `6` SecondOfMonth, `7` ThirdOfMonth, `8` LastOfMonth, `9` FourthOfMonth |
| `--which-bookings-to-update` | `1` UpdateThisBookingOnly, `2` UpdateFutureBookingsOnly, `3` UpdateAllBookings, `4` UpdateNotChargedBookings, `5` DeleteAllBookings, `6` DeleteBookingsAfterThis, `7` DeleteNotChargedBookings, `8` RevertAllCharges |

<!-- END:GENERATED entity=Bookings -->
