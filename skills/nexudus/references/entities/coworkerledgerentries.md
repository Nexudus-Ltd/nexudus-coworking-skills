# CoworkerLedgerEntries

<!-- BEGIN:GENERATED entity=CoworkerLedgerEntries -->

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

`--business-id`, `--coworker-id`, `--coworker-invoice-id`, `--description`, `--code`, `--debit`, `--from-debit` (range), `--to-debit` (range), `--credit`, `--from-credit` (range), `--to-credit` (range), `--payment-gateway-name`, `--payment-method-number`, `--transaction-date`, `--from-transaction-date` (range), `--to-transaction-date` (range), `--balance`, `--from-balance` (range), `--to-balance` (range), `--billed`, `--transaction-date-local`, `--from-transaction-date-local` (range), `--to-transaction-date-local` (range), `--connected-transaction-guid`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerLedgerEntry create options

`--business-id` (required), `--coworker-id` (required), `--coworker-invoice-id`, `--description` (required), `--code` (required), `--debit` (required), `--credit` (required), `--payment-gateway-name`, `--payment-method-number`, `--transaction-date`, `--balance` (required), `--billed`, `--transaction-date-local`, `--connected-transaction-guid`

#### CoworkerLedgerEntry update options

`--business-id`, `--coworker-id`, `--coworker-invoice-id`, `--description`, `--code`, `--debit`, `--credit`, `--payment-method-number`, `--transaction-date`, `--balance`, `--billed`, `--transaction-date-local`, `--connected-transaction-guid`

### CoworkerLedgerEntry (key fields)

`Id`, `CoworkerFullName`, `Description`, `Code`, `Debit`, `Credit`

<!-- END:GENERATED entity=CoworkerLedgerEntries -->
