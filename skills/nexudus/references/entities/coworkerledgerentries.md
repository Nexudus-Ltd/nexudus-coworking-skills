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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--coworker-id` | long |  |
| `--coworker-invoice-id` | long |  |
| `--description` | string | Description |
| `--code` | string | Ledger entry code |
| `--debit` | decimal | Debit amount |
| `--from-debit` | range | |
| `--to-debit` | range | |
| `--credit` | decimal | Credit amount |
| `--from-credit` | range | |
| `--to-credit` | range | |
| `--payment-gateway-name` | enum | Payment gateway name |
| `--payment-method-number` | string | Payment method number |
| `--transaction-date` | DateTime | Transaction date |
| `--from-transaction-date` | range | |
| `--to-transaction-date` | range | |
| `--balance` | decimal | Balance |
| `--from-balance` | range | |
| `--to-balance` | range | |
| `--billed` | bool | Whether this entry has been billed |
| `--transaction-date-local` | DateTime | Transaction date in the location's local time |
| `--from-transaction-date-local` | range | |
| `--to-transaction-date-local` | range | |
| `--connected-transaction-guid` | string | Connected transaction GUID |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerLedgerEntry create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--coworker-id` | long, required |  |
| `--coworker-invoice-id` | long |  |
| `--description` | string, required | Description |
| `--code` | string, required | Ledger entry code |
| `--debit` | decimal, required | Debit amount |
| `--credit` | decimal, required | Credit amount |
| `--payment-gateway-name` | enum | Payment gateway name |
| `--payment-method-number` | string | Payment method number |
| `--transaction-date` | DateTime | Transaction date |
| `--balance` | decimal, required | Balance |
| `--billed` | bool | Whether this entry has been billed |
| `--transaction-date-local` | DateTime | Transaction date in the location's local time |
| `--connected-transaction-guid` | string | Connected transaction GUID |

#### CoworkerLedgerEntry update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--coworker-id` | long |  |
| `--coworker-invoice-id` | long |  |
| `--description` | string | Description |
| `--code` | string | Ledger entry code |
| `--debit` | decimal | Debit amount |
| `--credit` | decimal | Credit amount |
| `--payment-method-number` | string | Payment method number |
| `--transaction-date` | DateTime | Transaction date |
| `--balance` | decimal | Balance |
| `--billed` | bool | Whether this entry has been billed |
| `--transaction-date-local` | DateTime | Transaction date in the location's local time |
| `--connected-transaction-guid` | string | Connected transaction GUID |

#### CoworkerLedgerEntry PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkerledgerentries update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerLedgerEntry (key fields)

`Id`, `CoworkerFullName`, `Description`, `Code`, `Debit`, `Credit`

<!-- END:GENERATED entity=CoworkerLedgerEntries -->
