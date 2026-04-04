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

`--coworker-id`, `--business-id`, `--quantity`, `--description`, `--invoice-line-display-as`, `--regular-charge`, `--discount-amount`, `--credit-amount`, `--due-date`, `--total-amount`, `--purchase-order`, `--tax-rate-id`, `--financial-account-id`, `--invoiced`, `--sale-date`, `--from-team-member`, `--coworker-extra-service-name`, `--coworker-time-pass-name`, `--coworker-product-name`, `--tariff-name`, `--coworker-product-unique-id`, `--booking-unique-id`, `--repeat-from`, `--repeat-until`

#### Charge create options

`--coworker-id` (required), `--business-id` (required), `--quantity` (required), `--description`, `--invoice-line-display-as`, `--regular-charge`, `--discount-amount` (required), `--credit-amount` (required), `--due-date`, `--total-amount` (required), `--purchase-order`, `--tax-rate-id`, `--financial-account-id`, `--invoiced`, `--sale-date`, `--from-team-member`, `--coworker-extra-service-name`, `--coworker-time-pass-name`, `--coworker-product-name`, `--tariff-name`, `--coworker-product-unique-id`, `--booking-unique-id`, `--repeat-from`, `--repeat-until`

#### Charge update options

`--coworker-id`, `--business-id`, `--quantity`, `--description`, `--invoice-line-display-as`, `--regular-charge`, `--discount-amount`, `--credit-amount`, `--due-date`, `--total-amount`, `--purchase-order`, `--tax-rate-id`, `--financial-account-id`, `--invoiced`, `--sale-date`, `--from-team-member`, `--coworker-extra-service-name`, `--coworker-time-pass-name`, `--coworker-product-name`, `--tariff-name`, `--coworker-product-unique-id`, `--booking-unique-id`, `--repeat-from`, `--repeat-until`

### Charge (key fields)

`Id`, `ChargeNumber`, `Description`, `TotalAmount`, `Invoiced`

<!-- END:GENERATED entity=Charges -->
