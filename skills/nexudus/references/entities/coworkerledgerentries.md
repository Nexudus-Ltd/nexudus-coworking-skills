# CoworkerLedgerEntries

<!-- BEGIN:GENERATED entity=CoworkerLedgerEntries -->

A **CoworkerLedgerEntry** is an individual financial transaction line in a customer's ledger. Ledger entries record debits, credits, and the running balance between a location and a customer.

Each entry can be linked to a `CoworkerInvoice` and carries a `PaymentGatewayName` that identifies which payment provider processed the transaction.

The ledger balance reflects the net financial position between the location and the customer:
- A **positive** balance means the customer owes money (unpaid invoices).
- A **negative** balance means the customer has credited payments that will be applied to future invoices.
- A balance of **0** means the account is settled with no outstanding invoices or credits.

CoworkerLedgerEntries support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerledgerentries list --agent` | List all coworkerledgerentries |
| `nexudus coworkerledgerentries list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerledgerentries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerledgerentries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerledgerentries list --description <value> --code <value> --agent` | Filter coworkerledgerentries by properties |
| `nexudus coworkerledgerentries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerledgerentries get <id> --agent` | Get single coworkerledgerentry |
| `nexudus coworkerledgerentries create --business-id <value> --coworker-id <value> --description <value> --code <value> --debit <value> --credit <value> --balance <value> --agent` | Create coworkerledgerentry |
| `nexudus coworkerledgerentries update <id> --name "New Name" --agent` | Update coworkerledgerentry |
| `nexudus coworkerledgerentries delete <id> --yes --agent` | Delete coworkerledgerentry (no prompt) |

#### CoworkerLedgerEntry list filter options

`--business-id` (long), `--coworker-id` (long), `--coworker-invoice-id` (long), `--description`, `--code`, `--debit` (decimal), `--from-debit` (range), `--to-debit` (range), `--credit` (decimal), `--from-credit` (range), `--to-credit` (range), `--payment-gateway-name` (enum), `--payment-method-number`, `--transaction-date` (DateTime), `--from-transaction-date` (range), `--to-transaction-date` (range), `--balance` (decimal), `--from-balance` (range), `--to-balance` (range), `--billed` (bool), `--transaction-date-local` (DateTime), `--from-transaction-date-local` (range), `--to-transaction-date-local` (range), `--connected-transaction-guid`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerLedgerEntry create options

`--business-id` (long, required), `--coworker-id` (long, required), `--coworker-invoice-id` (long), `--description` (required), `--code` (required), `--debit` (decimal, required), `--credit` (decimal, required), `--payment-gateway-name` (enum), `--payment-method-number`, `--transaction-date` (DateTime), `--balance` (decimal, required), `--billed` (bool), `--transaction-date-local` (DateTime), `--connected-transaction-guid`

#### CoworkerLedgerEntry update options

`--business-id` (long), `--coworker-id` (long), `--coworker-invoice-id` (long), `--description`, `--code`, `--debit` (decimal), `--credit` (decimal), `--payment-method-number`, `--transaction-date` (DateTime), `--balance` (decimal), `--billed` (bool), `--transaction-date-local` (DateTime), `--connected-transaction-guid`

### CoworkerLedgerEntry (key fields)

`Id`, `CoworkerFullName`, `Description`, `Code`, `Debit`, `Credit`

<!-- END:GENERATED entity=CoworkerLedgerEntries -->
