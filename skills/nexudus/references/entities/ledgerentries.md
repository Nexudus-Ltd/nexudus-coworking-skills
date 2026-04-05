# LedgerEntries

<!-- BEGIN:GENERATED entity=LedgerEntries -->

A **LedgerEntry** is a credit or debit record in the financial ledger for invoices issued by Nexudus to the operator (the business running the coworking space).

Each entry records either a debit or a credit against a location. Entries are identified by an optional `Code` for grouping or reconciliation and a free-text `Description` explaining the transaction.

LedgerEntries support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus ledgerentries list --agent` | List all ledgerentries |
| `nexudus ledgerentries list --id <id> --agent` | Filter by single ID |
| `nexudus ledgerentries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus ledgerentries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus ledgerentries list --code <value> --description <value> --agent` | Filter ledgerentries by properties |
| `nexudus ledgerentries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus ledgerentries get <id> --agent` | Get single ledgerentry |

#### LedgerEntry list filter options

`--business-id`, `--code`, `--description`, `--debit`, `--from-debit` (range), `--to-debit` (range), `--credit`, `--from-credit` (range), `--to-credit` (range), `--balance`, `--from-balance` (range), `--to-balance` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

### LedgerEntry (key fields)

`Id`, `Code`, `Description`, `Debit`, `Credit`

<!-- END:GENERATED entity=LedgerEntries -->
