# Charges

<!-- BEGIN:GENERATED entity=Charges -->

A **Charge** is a generic debit item applied to a customer account. Prefer more specific entities when available — use `CoworkerProduct` for product sales, `Booking` for room/resource bookings, `EventAttendee` for event registrations, and `CoworkerContract` for recurring plan charges.

Charges can reference the originating sale from another entity via its `UniqueId` (a GUID, not an integer ID). This is how items billed to a non-paying team member are passed through to the team's paying member: the charge appears on the paying member's account with a `UniqueId` reference back to the original `CoworkerProduct`, `Booking`, `EventAttendee`, or `CoworkerTimePass`.

Booking-related extra-service charges are represented by `CoworkerExtraService` records and referenced via `CoworkerExtraServiceUniqueId`.

Charges support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus charges list --agent` | List all charges |
| `nexudus charges list --id <id> --agent` | Filter by single ID |
| `nexudus charges list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus charges list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus charges list --description <value> --total-amount <value> --agent` | Filter charges by properties |
| `nexudus charges list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus charges get <id> --agent` | Get single charge |
| `nexudus charges create --coworker-id <value> --business-id <value> --quantity <value> --discount-amount <value> --credit-amount <value> --total-amount <value> --agent` | Create charge |
| `nexudus charges update <id> --name "New Name" --agent` | Update charge |
| `nexudus charges delete <id> --yes --agent` | Delete charge (no prompt) |

#### Charge list filter options

`--coworker-id` (long), `--business-id` (long), `--quantity` (int), `--from-quantity` (range), `--to-quantity` (range), `--description`, `--invoice-line-display-as`, `--regular-charge` (bool), `--discount-amount` (decimal), `--from-discount-amount` (range), `--to-discount-amount` (range), `--credit-amount` (decimal), `--from-credit-amount` (range), `--to-credit-amount` (range), `--due-date` (DateTime), `--from-due-date` (range), `--to-due-date` (range), `--total-amount` (decimal), `--from-total-amount` (range), `--to-total-amount` (range), `--purchase-order`, `--tax-rate-id` (long), `--financial-account-id` (long), `--invoiced` (bool), `--sale-date` (DateTime), `--from-sale-date` (range), `--to-sale-date` (range), `--from-team-member` (bool), `--coworker-extra-service-name`, `--coworker-time-pass-name`, `--coworker-product-name`, `--tariff-name`, `--coworker-product-unique-id`, `--booking-unique-id`, `--repeat-from` (DateTime), `--from-repeat-from` (range), `--to-repeat-from` (range), `--repeat-until` (DateTime), `--from-repeat-until` (range), `--to-repeat-until` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Charge create options

`--coworker-id` (long, required), `--business-id` (long, required), `--quantity` (int, required), `--description`, `--invoice-line-display-as`, `--regular-charge` (bool), `--discount-amount` (decimal, required), `--credit-amount` (decimal, required), `--due-date` (DateTime), `--total-amount` (decimal, required), `--purchase-order`, `--tax-rate-id` (long), `--financial-account-id` (long), `--invoiced` (bool), `--sale-date` (DateTime), `--from-team-member` (bool), `--coworker-extra-service-name`, `--coworker-time-pass-name`, `--coworker-product-name`, `--tariff-name`, `--coworker-product-unique-id`, `--booking-unique-id`, `--repeat-from` (DateTime), `--repeat-until` (DateTime)

#### Charge update options

`--coworker-id` (long), `--business-id` (long), `--quantity` (int), `--description`, `--invoice-line-display-as`, `--regular-charge` (bool), `--discount-amount` (decimal), `--credit-amount` (decimal), `--due-date` (DateTime), `--total-amount` (decimal), `--purchase-order`, `--tax-rate-id` (long), `--financial-account-id` (long), `--invoiced` (bool), `--sale-date` (DateTime), `--from-team-member` (bool), `--coworker-extra-service-name`, `--coworker-time-pass-name`, `--coworker-product-name`, `--tariff-name`, `--coworker-product-unique-id`, `--booking-unique-id`, `--repeat-from` (DateTime), `--repeat-until` (DateTime)

### Charge (key fields)

`Id`, `ChargeNumber`, `Description`, `TotalAmount`, `Invoiced`

<!-- END:GENERATED entity=Charges -->
