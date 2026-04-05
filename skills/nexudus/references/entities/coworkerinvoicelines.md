# CoworkerInvoiceLines

<!-- BEGIN:GENERATED entity=CoworkerInvoiceLines -->

A **CoworkerInvoiceLine** represents an individual line item on a customer invoice. Each line captures the description, quantity, amounts, tax, and an optional link to the sale item that generated it.

Properties ending in `UniqueId` link the line to the originating sale record using its GUID `UniqueId` property (not the integer ID). Only one of these will be populated per line:

| UniqueId property                | Source entity        |
| -------------------------------- | -------------------- |
| `CoworkerContractUniqueId`       | CoworkerContract     |
| `ContractDepositUniqueId`        | ContractDeposit      |
| `BookingUniqueId`                | Booking              |
| `CoworkerExtraServiceUniqueId`   | CoworkerExtraService |
| `CoworkerTimePassUniqueId`       | CoworkerTimePass     |
| `CoworkerChargeUniqueId`         | Charge               |
| `CoworkerProductUniqueId`        | CoworkerProduct      |
| `EventAttendeeUniqueId`          | EventAttendee        |

CoworkerInvoiceLines support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkerinvoicelines list --agent` | List all coworkerinvoicelines |
| `nexudus coworkerinvoicelines list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerinvoicelines list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerinvoicelines list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerinvoicelines list --description <value> --quantity <value> --agent` | Filter coworkerinvoicelines by properties |
| `nexudus coworkerinvoicelines list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerinvoicelines get <id> --agent` | Get single coworkerinvoiceline |
| `nexudus coworkerinvoicelines update <id> --name "New Name" --agent` | Update coworkerinvoiceline |

#### CoworkerInvoiceLine list filter options

`--coworker-invoice-id`, `--description`, `--display-as`, `--tax-category-name`, `--quantity`, `--from-quantity` (range), `--to-quantity` (range), `--sub-total`, `--from-sub-total` (range), `--to-sub-total` (range), `--tax-amount`, `--from-tax-amount` (range), `--to-tax-amount` (range), `--tax-rate`, `--from-tax-rate` (range), `--to-tax-rate` (range), `--financial-account-code`, `--financial-account-name`, `--issued-by-unique-id`, `--cancelled-coworker-invoice-line-unique-id`, `--created-on-local`, `--from-created-on-local` (range), `--to-created-on-local` (range), `--refunded-on-local`, `--from-refunded-on-local` (range), `--to-refunded-on-local` (range), `--sale-date-local`, `--from-sale-date-local` (range), `--to-sale-date-local` (range), `--purchase-order`, `--credit-amount`, `--from-credit-amount` (range), `--to-credit-amount` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerInvoiceLine update options

`--coworker-invoice-id`, `--description`, `--display-as`, `--tax-category-name`, `--quantity`, `--sub-total`, `--tax-amount`, `--tax-rate`, `--financial-account-code`, `--financial-account-name`, `--issued-by-unique-id`, `--cancelled-coworker-invoice-line-unique-id`, `--created-on-local`, `--refunded-on-local`, `--sale-date-local`, `--purchase-order`, `--credit-amount`

### CoworkerInvoiceLine (key fields)

`Id`, `CoworkerInvoiceInvoiceNumber`, `Description`, `Quantity`, `SubTotal`

<!-- END:GENERATED entity=CoworkerInvoiceLines -->
