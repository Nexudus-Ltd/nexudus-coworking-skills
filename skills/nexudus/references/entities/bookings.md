# Bookings

<!-- BEGIN:GENERATED entity=Bookings -->

A **Booking** is a reservation for a specific `Resource` and, optionally, for a customer (`CoworkerId`) and a desk or unit in the floor plan (`FloorPlanDeskId`).

**Charging vs Invoicing** — When a booking is charged (confusingly labelled `Invoiced` in the booking entity), a charge is posted to the customer account as a `CoworkerExtraService` with the calculated price. If the booking has no fixed rate (`ExtraServiceId = null`), Nexudus calculates the rate automatically based on the resource type, booking parameters and customer. A booking is actually invoiced when the `CoworkerExtraService` associated with it is invoiced.

- `InvoiceThisCoworker = true` means the booking is charged to the customer making it rather than their paying member (if any).
- `Tentative` bookings must be approved by an administrator before being confirmed or charged. They still block the calendar.
- `Online` bookings are those made via the portal or the app.

**Repeating bookings** — `RepeatBooking` and all repeat-configuration fields (`Repeats`, `RepeatEvery`, `RepeatUntil`, `RepeatOn*`) are create-only. Once a booking series is created, only `WhichBookingsToUpdate` can be used to update or delete bookings in the series. No new bookings can be added to an existing series.

**Pricing overrides** — `OverridePrice` lets an admin set a fixed price for the booking, regardless of what extra service (rate) is associated with it.

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
| `nexudus bookings get <id> --agent` | Get single booking |
| `nexudus bookings create --resource-id <value> --from-time <value> --to-time <value> --repeats <value> --which-bookings-to-update <value> --agent` | Create booking |
| `nexudus bookings update <id> --name "New Name" --agent` | Update booking |
| `nexudus bookings delete <id> --yes --agent` | Delete booking (no prompt) |
| `nexudus bookings run-command <key> <ids> --agent` | Run entity command |

#### Booking list filter options

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
| `--internal-notes` | string | Internal notes |
| `--charge-now` | bool | Charge immediately |
| `--invoice-now` | bool | Invoice immediately |
| `--invoice-this-coworker` | bool | Charge the booking to the customer making it rather than their paying member (if any) |
| `--do-not-use-booking-credit` | bool | Do not use booking credit |
| `--purchase-order` | string | Purchase order |
| `--discount-code` | string | Discount code |
| `--last-notification-time` | DateTime |  |
| `--from-last-notification-time` | range | |
| `--to-last-notification-time` | range | |
| `--google-calendar-id` | string |  |
| `--google-event-id` | string |  |
| `--office365-event-id` | string |  |
| `--public-google-event-id` | string |  |
| `--tentative` | bool | Tentative booking. Must be approved by an administrator before confirmed or charged. Tentative bookings still block the calendar |
| `--teams-at-booking` | string | Teams at the time of booking |
| `--tariff-at-booking` | string | Tariff at the time of booking |
| `--repeat-series-unique-id` | string |  |
| `--repeat-booking` | bool | Create a repeating booking series. Create-only: once created, only WhichBookingsToUpdate can be used to update the series. No new bookings can be added to the series |
| `--repeats` | enum | Repeat cycle. Create-only |
| `--which-bookings-to-update` | enum | Action to apply when updating or deleting bookings in a repeated series. This is the only field that can modify a series after creation |
| `--repeat-every` | int | Repeat every N periods. Create-only |
| `--from-repeat-every` | range | |
| `--to-repeat-every` | range | |
| `--repeat-until` | DateTime | Repeat until date. Create-only |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--repeat-on-mondays` | bool | Repeat on Mondays. Create-only |
| `--repeat-on-tuesdays` | bool | Repeat on Tuesdays. Create-only |
| `--repeat-on-wednesdays` | bool | Repeat on Wednesdays. Create-only |
| `--repeat-on-thursdays` | bool | Repeat on Thursdays. Create-only |
| `--repeat-on-fridays` | bool | Repeat on Fridays. Create-only |
| `--repeat-on-saturdays` | bool | Repeat on Saturdays. Create-only |
| `--repeat-on-sundays` | bool | Repeat on Sundays. Create-only |
| `--reminded` | bool |  |
| `--mrm-reminded` | bool |  |
| `--override-price` | decimal | Admin-set fixed price for the booking, regardless of what extra service (rate) is associated with it |
| `--from-override-price` | range | |
| `--to-override-price` | range | |
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
| `--coworker-extra-service-price` | decimal |  |
| `--from-coworker-extra-service-price` | range | |
| `--to-coworker-extra-service-price` | range | |
| `--include-zoom-invite` | bool | Include Zoom invite |
| `--zoom-event-data` | string |  |
| `--office365-admin-event-id` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Booking create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required |  |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--extra-service-id` | long |  |
| `--from-time` | DateTime, required | Booking start time |
| `--to-time` | DateTime, required | Booking end time |
| `--notes` | string | Notes |
| `--internal-notes` | string | Internal notes |
| `--charge-now` | bool | Charge immediately |
| `--invoice-now` | bool | Invoice immediately |
| `--invoice-this-coworker` | bool | Charge the booking to the customer making it rather than their paying member (if any) |
| `--do-not-use-booking-credit` | bool | Do not use booking credit |
| `--purchase-order` | string | Purchase order |
| `--discount-code` | string | Discount code |
| `--last-notification-time` | DateTime |  |
| `--google-calendar-id` | string |  |
| `--google-event-id` | string |  |
| `--office365-event-id` | string |  |
| `--public-google-event-id` | string |  |
| `--tentative` | bool | Tentative booking. Must be approved by an administrator before confirmed or charged. Tentative bookings still block the calendar |
| `--teams-at-booking` | string | Teams at the time of booking |
| `--tariff-at-booking` | string | Tariff at the time of booking |
| `--repeat-series-unique-id` | string |  |
| `--repeat-booking` | bool | Create a repeating booking series. Create-only: once created, only WhichBookingsToUpdate can be used to update the series. No new bookings can be added to the series |
| `--repeats` | enum, required | Repeat cycle. Create-only |
| `--which-bookings-to-update` | enum, required | Action to apply when updating or deleting bookings in a repeated series. This is the only field that can modify a series after creation |
| `--repeat-every` | int | Repeat every N periods. Create-only |
| `--repeat-until` | DateTime | Repeat until date. Create-only |
| `--repeat-on-mondays` | bool | Repeat on Mondays. Create-only |
| `--repeat-on-tuesdays` | bool | Repeat on Tuesdays. Create-only |
| `--repeat-on-wednesdays` | bool | Repeat on Wednesdays. Create-only |
| `--repeat-on-thursdays` | bool | Repeat on Thursdays. Create-only |
| `--repeat-on-fridays` | bool | Repeat on Fridays. Create-only |
| `--repeat-on-saturdays` | bool | Repeat on Saturdays. Create-only |
| `--repeat-on-sundays` | bool | Repeat on Sundays. Create-only |
| `--reminded` | bool |  |
| `--mrm-reminded` | bool |  |
| `--override-price` | decimal | Admin-set fixed price for the booking, regardless of what extra service (rate) is associated with it |
| `--kisi-key-id` | int |  |
| `--start-scheduled-job-id` | string |  |
| `--end-scheduled-job-id` | string |  |
| `--billed` | bool |  |
| `--from-time-local` | DateTime |  |
| `--to-time-local` | DateTime |  |
| `--invoice-date-local` | DateTime |  |
| `--coworker-extra-service-price` | decimal |  |
| `--include-zoom-invite` | bool | Include Zoom invite |
| `--zoom-event-data` | string |  |
| `--office365-admin-event-id` | string |  |
| `--booking-products` | JSON array or @filepath | Products to include with this booking |
| `--booking-visitors` | JSON array or @filepath | Visitors to add to this booking |

#### Booking update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long |  |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--extra-service-id` | long |  |
| `--from-time` | DateTime | Booking start time |
| `--to-time` | DateTime | Booking end time |
| `--notes` | string | Notes |
| `--charge-now` | bool | Charge immediately |
| `--invoice-now` | bool | Invoice immediately |
| `--invoice-this-coworker` | bool | Charge the booking to the customer making it rather than their paying member (if any) |
| `--do-not-use-booking-credit` | bool | Do not use booking credit |
| `--purchase-order` | string | Purchase order |
| `--discount-code` | string | Discount code |
| `--last-notification-time` | DateTime |  |
| `--google-calendar-id` | string |  |
| `--google-event-id` | string |  |
| `--office365-event-id` | string |  |
| `--public-google-event-id` | string |  |
| `--tentative` | bool | Tentative booking. Must be approved by an administrator before confirmed or charged. Tentative bookings still block the calendar |
| `--teams-at-booking` | string | Teams at the time of booking |
| `--tariff-at-booking` | string | Tariff at the time of booking |
| `--which-bookings-to-update` | enum | Action to apply when updating or deleting bookings in a repeated series. This is the only field that can modify a series after creation |
| `--reminded` | bool |  |
| `--mrm-reminded` | bool |  |
| `--override-price` | decimal | Admin-set fixed price for the booking, regardless of what extra service (rate) is associated with it |
| `--kisi-key-id` | int |  |
| `--start-scheduled-job-id` | string |  |
| `--end-scheduled-job-id` | string |  |
| `--billed` | bool |  |
| `--from-time-local` | DateTime |  |
| `--to-time-local` | DateTime |  |
| `--invoice-date-local` | DateTime |  |
| `--coworker-extra-service-price` | decimal |  |
| `--include-zoom-invite` | bool | Include Zoom invite |
| `--zoom-event-data` | string |  |
| `--office365-admin-event-id` | string |  |
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
