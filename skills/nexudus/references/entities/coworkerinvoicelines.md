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
| `nexudus coworkerinvoicelines list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerinvoicelines get <id> --agent` | Get single coworkerinvoiceline |
| `nexudus coworkerinvoicelines update <id> --name "New Name" --agent` | Update coworkerinvoiceline |

#### CoworkerInvoiceLine list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the coworker invoice linked to this record |
| `--description` | string | Line item description shown internally |
| `--display-as` | string | Override text displayed on the printed/emailed invoice instead of the description |
| `--tax-category-name` | string | Name of the tax category applied to this line |
| `--quantity` | int | Number of units for this line item |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--sub-total` | decimal | Line subtotal before tax (unit price x quantity) |
| `--from-sub-total` | range | |
| `--to-sub-total` | range | |
| `--tax-amount` | decimal | Tax amount calculated for this line |
| `--from-tax-amount` | range | |
| `--to-tax-amount` | range | |
| `--tax-rate` | decimal | Tax rate percentage applied to this line |
| `--from-tax-rate` | range | |
| `--to-tax-rate` | range | |
| `--financial-account-code` | string | Code of the financial account (revenue category) for this line |
| `--financial-account-name` | string | Name of the financial account (revenue category) for this line |
| `--issued-by-unique-id` | string | ID of the issued by unique associated with this record |
| `--cancelled-coworker-invoice-line-unique-id` | string | ID of the cancelled coworker invoice line unique associated with this record |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--from-created-on-local` | range | |
| `--to-created-on-local` | range | |
| `--refunded-on-local` | DateTime | Date/time value for refunded on local |
| `--from-refunded-on-local` | range | |
| `--to-refunded-on-local` | range | |
| `--sale-date-local` | DateTime | Date/time value for sale date local |
| `--from-sale-date-local` | range | |
| `--to-sale-date-local` | range | |
| `--purchase-order` | string | Purchase order reference for this line |
| `--credit-amount` | decimal | Credit amount applied to this line |
| `--from-credit-amount` | range | |
| `--to-credit-amount` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerInvoiceLine sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (ascending).

#### CoworkerInvoiceLine update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the coworker invoice linked to this record |
| `--description` | string | Line item description shown internally |
| `--display-as` | string | Override text displayed on the printed/emailed invoice instead of the description |
| `--tax-category-name` | string | Name of the tax category applied to this line |
| `--quantity` | int | Number of units for this line item |
| `--sub-total` | decimal | Line subtotal before tax (unit price x quantity) |
| `--tax-amount` | decimal | Tax amount calculated for this line |
| `--tax-rate` | decimal | Tax rate percentage applied to this line |
| `--financial-account-code` | string | Code of the financial account (revenue category) for this line |
| `--financial-account-name` | string | Name of the financial account (revenue category) for this line |
| `--issued-by-unique-id` | string | ID of the issued by unique associated with this record |
| `--cancelled-coworker-invoice-line-unique-id` | string | ID of the cancelled coworker invoice line unique associated with this record |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--refunded-on-local` | DateTime | Date/time value for refunded on local |
| `--sale-date-local` | DateTime | Date/time value for sale date local |
| `--purchase-order` | string | Purchase order reference for this line |
| `--credit-amount` | decimal | Credit amount applied to this line |

### CoworkerInvoiceLine (key fields)

`Id`, `CoworkerInvoiceInvoiceNumber`, `Description`, `Quantity`, `SubTotal`

<!-- END:GENERATED entity=CoworkerInvoiceLines -->
