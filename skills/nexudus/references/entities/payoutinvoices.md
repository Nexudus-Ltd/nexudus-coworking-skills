# PayoutInvoices

<!-- BEGIN:GENERATED entity=PayoutInvoices -->

A **PayoutInvoice** represents an invoice generated for payout purposes, tracking payments due to or from reseller accounts or partner locations.

PayoutInvoices support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus payoutinvoices list --agent` | List all payoutinvoices |
| `nexudus payoutinvoices list --id <id> --agent` | Filter by single ID |
| `nexudus payoutinvoices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus payoutinvoices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus payoutinvoices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus payoutinvoices get <id> --agent` | Get single payoutinvoice |
| `nexudus payoutinvoices create  --agent` | Create payoutinvoice |
| `nexudus payoutinvoices update <id> --name "New Name" --agent` | Update payoutinvoice |
| `nexudus payoutinvoices delete <id> --yes --agent` | Delete payoutinvoice (no prompt) |

#### PayoutInvoice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### PayoutInvoice create options

| Option | Type | Description |
| --- | --- | --- |

#### PayoutInvoice update options

| Option | Type | Description |
| --- | --- | --- |

<!-- END:GENERATED entity=PayoutInvoices -->
