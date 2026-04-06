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

`--resource-id`, `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time`, `--from-from-time` (range), `--to-from-time` (range), `--to-time`, `--from-to-time` (range), `--to-to-time` (range), `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--last-notification-time`, `--from-last-notification-time` (range), `--to-last-notification-time` (range), `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative`, `--teams-at-booking`, `--tariff-at-booking`, `--repeat-series-unique-id`, `--repeat-booking`, `--repeats`, `--which-bookings-to-update`, `--repeat-every`, `--from-repeat-every` (range), `--to-repeat-every` (range), `--repeat-until`, `--from-repeat-until` (range), `--to-repeat-until` (range), `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--reminded`, `--mrm-reminded`, `--override-price`, `--from-override-price` (range), `--to-override-price` (range), `--kisi-key-id`, `--from-kisi-key-id` (range), `--to-kisi-key-id` (range), `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed`, `--from-time-local`, `--from-from-time-local` (range), `--to-from-time-local` (range), `--to-time-local`, `--from-to-time-local` (range), `--to-to-time-local` (range), `--invoice-date-local`, `--from-invoice-date-local` (range), `--to-invoice-date-local` (range), `--coworker-extra-service-price`, `--from-coworker-extra-service-price` (range), `--to-coworker-extra-service-price` (range), `--include-zoom-invite`, `--zoom-event-data`, `--office365-admin-event-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Booking create options

`--resource-id` (required), `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time` (required), `--to-time` (required), `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--last-notification-time`, `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative`, `--teams-at-booking`, `--tariff-at-booking`, `--repeat-series-unique-id`, `--repeat-booking`, `--repeats` (required), `--which-bookings-to-update` (required), `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--reminded`, `--mrm-reminded`, `--override-price`, `--kisi-key-id`, `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed`, `--from-time-local`, `--to-time-local`, `--invoice-date-local`, `--coworker-extra-service-price`, `--include-zoom-invite`, `--zoom-event-data`, `--office365-admin-event-id`, `--booking-products` (JSON array or @filepath), `--booking-visitors` (JSON array or @filepath)

#### Booking update options

`--resource-id`, `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time`, `--to-time`, `--notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--last-notification-time`, `--google-calendar-id`, `--google-event-id`, `--office365-event-id`, `--public-google-event-id`, `--tentative`, `--teams-at-booking`, `--tariff-at-booking`, `--which-bookings-to-update`, `--reminded`, `--mrm-reminded`, `--override-price`, `--kisi-key-id`, `--start-scheduled-job-id`, `--end-scheduled-job-id`, `--billed`, `--from-time-local`, `--to-time-local`, `--invoice-date-local`, `--coworker-extra-service-price`, `--include-zoom-invite`, `--zoom-event-data`, `--office365-admin-event-id`, `--booking-products` (JSON array or @filepath), `--booking-visitors` (JSON array or @filepath)

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
