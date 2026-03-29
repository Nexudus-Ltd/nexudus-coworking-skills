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

| Command | Description |
| --- | --- |
| `nexudus bookings list --agent` | List all bookings |
| `nexudus bookings list --query "search" --agent` | Search bookings by name |
| `nexudus bookings list --page 2 --size 10 --agent` | Paginated list |
| `nexudus bookings get <id> --agent` | Get single booking |
| `nexudus bookings create --resource-id <value> --from-time <value> --to-time <value> --agent` | Create booking |
| `nexudus bookings update <id> --name "New Name" --agent` | Update booking |
| `nexudus bookings delete <id> --yes --agent` | Delete booking (no prompt) |

#### Booking create options

`--resource-id` (required), `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time` (required), `--to-time` (required), `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--tentative`, `--online`, `--repeat-booking`, `--repeats`, `--which-bookings-to-update`, `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--override-price`, `--include-zoom-invite`, `--cancel-if-not-paid`, `--cancel-if-not-checked-in`, `--max-occupancy`, `--booking-products` (JSON array or @filepath), `--booking-visitors` (JSON array or @filepath)

#### Booking update options

`--resource-id`, `--floor-plan-desk-id`, `--coworker-id`, `--extra-service-id`, `--from-time`, `--to-time`, `--notes`, `--internal-notes`, `--charge-now`, `--invoice-now`, `--invoice-this-coworker`, `--do-not-use-booking-credit`, `--purchase-order`, `--discount-code`, `--tentative`, `--online`, `--repeat-booking`, `--repeats`, `--which-bookings-to-update`, `--repeat-every`, `--repeat-until`, `--repeat-on-mondays`, `--repeat-on-tuesdays`, `--repeat-on-wednesdays`, `--repeat-on-thursdays`, `--repeat-on-fridays`, `--repeat-on-saturdays`, `--repeat-on-sundays`, `--override-price`, `--include-zoom-invite`, `--cancel-if-not-paid`, `--cancel-if-not-checked-in`, `--max-occupancy`, `--booking-products` (JSON array or @filepath), `--booking-visitors` (JSON array or @filepath)

### Booking (key fields)

`Id`, `ResourceId`, `ResourceName`, `CoworkerId`, `CoworkerFullName`, `FromTime`, `ToTime`, `Tentative`, `Invoiced`

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
