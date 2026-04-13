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

`--resource-id` (long), `--floor-plan-desk-id` (long), `--coworker-id` (long), `--extra-service-id` (long), `--from-time` (DateTime), `--from-from-time` (range), `--to-from-time` (range), `--to-time` (DateTime), `--from-to-time` (range), `--to-to-time` (range), `--notes`, `--internal-notes`, `--charge-now` (bool), `--invoice-now` (bool), `--invoice-this-coworker` (bool), `--do-not-use-booking-credit` (bool), `--purchase-order`, `--discount-code`, `--last-notification-time` (DateTime), `--from-last-notification-time` (range), `--to-last-notification-time` (range), `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative` (bool), `--teams-at-booking`, `--tariff-at-booking`, `--repeat-series-unique-id`, `--repeat-booking` (bool), `--repeats` (enum), `--which-bookings-to-update` (enum), `--repeat-every` (int), `--from-repeat-every` (range), `--to-repeat-every` (range), `--repeat-until` (DateTime), `--from-repeat-until` (range), `--to-repeat-until` (range), `--repeat-on-mondays` (bool), `--repeat-on-tuesdays` (bool), `--repeat-on-wednesdays` (bool), `--repeat-on-thursdays` (bool), `--repeat-on-fridays` (bool), `--repeat-on-saturdays` (bool), `--repeat-on-sundays` (bool), `--reminded` (bool), `--mrm-reminded` (bool), `--override-price` (decimal), `--from-override-price` (range), `--to-override-price` (range), `--kisi-key-id` (int), `--from-kisi-key-id` (range), `--to-kisi-key-id` (range), `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed` (bool), `--from-time-local` (DateTime), `--from-from-time-local` (range), `--to-from-time-local` (range), `--to-time-local` (DateTime), `--from-to-time-local` (range), `--to-to-time-local` (range), `--invoice-date-local` (DateTime), `--from-invoice-date-local` (range), `--to-invoice-date-local` (range), `--coworker-extra-service-price` (decimal), `--from-coworker-extra-service-price` (range), `--to-coworker-extra-service-price` (range), `--include-zoom-invite` (bool), `--zoom-event-data`, `--office365-admin-event-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Booking create options

`--resource-id` (long, required), `--floor-plan-desk-id` (long), `--coworker-id` (long), `--extra-service-id` (long), `--from-time` (DateTime, required), `--to-time` (DateTime, required), `--notes`, `--internal-notes`, `--charge-now` (bool), `--invoice-now` (bool), `--invoice-this-coworker` (bool), `--do-not-use-booking-credit` (bool), `--purchase-order`, `--discount-code`, `--last-notification-time` (DateTime), `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative` (bool), `--teams-at-booking`, `--tariff-at-booking`, `--repeat-series-unique-id`, `--repeat-booking` (bool), `--repeats` (enum, required), `--which-bookings-to-update` (enum, required), `--repeat-every` (int), `--repeat-until` (DateTime), `--repeat-on-mondays` (bool), `--repeat-on-tuesdays` (bool), `--repeat-on-wednesdays` (bool), `--repeat-on-thursdays` (bool), `--repeat-on-fridays` (bool), `--repeat-on-saturdays` (bool), `--repeat-on-sundays` (bool), `--reminded` (bool), `--mrm-reminded` (bool), `--override-price` (decimal), `--kisi-key-id` (int), `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed` (bool), `--from-time-local` (DateTime), `--to-time-local` (DateTime), `--invoice-date-local` (DateTime), `--coworker-extra-service-price` (decimal), `--include-zoom-invite` (bool), `--zoom-event-data`, `--office365-admin-event-id`, `--booking-products` (JSON array or @filepath), `--booking-visitors` (JSON array or @filepath)

#### Booking update options

`--resource-id` (long), `--floor-plan-desk-id` (long), `--coworker-id` (long), `--extra-service-id` (long), `--from-time` (DateTime), `--to-time` (DateTime), `--notes`, `--charge-now` (bool), `--invoice-now` (bool), `--invoice-this-coworker` (bool), `--do-not-use-booking-credit` (bool), `--purchase-order`, `--discount-code`, `--last-notification-time` (DateTime), `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative` (bool), `--teams-at-booking`, `--tariff-at-booking`, `--which-bookings-to-update` (enum), `--reminded` (bool), `--mrm-reminded` (bool), `--override-price` (decimal), `--kisi-key-id` (int), `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed` (bool), `--from-time-local` (DateTime), `--to-time-local` (DateTime), `--invoice-date-local` (DateTime), `--coworker-extra-service-price` (decimal), `--include-zoom-invite` (bool), `--zoom-event-data`, `--office365-admin-event-id`, `--booking-products` (JSON array or @filepath), `--booking-visitors` (JSON array or @filepath)

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
