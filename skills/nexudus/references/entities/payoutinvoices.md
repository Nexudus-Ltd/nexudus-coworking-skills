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
| `nexudus payoutinvoices list --invoice-id <value> --invoice-invoice-number <value> --agent` | Filter payoutinvoices by properties |
| `nexudus payoutinvoices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus payoutinvoices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus payoutinvoices get <id> --agent` | Get single payoutinvoice |
| `nexudus payoutinvoices create  --agent` | Create payoutinvoice |
| `nexudus payoutinvoices update <id> --name "New Name" --agent` | Update payoutinvoice |
| `nexudus payoutinvoices delete <id> --yes --agent` | Delete payoutinvoice (no prompt) |

#### PayoutInvoice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--invoice-id` | long | ID of the invoice linked to this record |
| `--invoice-invoice-number` | string | The invoice invoice number value for this payout invoice |
| `--invoice-reseller-amount` | decimal | The invoice reseller amount value for this payout invoice |
| `--from-invoice-reseller-amount` | range | |
| `--to-invoice-reseller-amount` | range | |
| `--invoice-created-on` | string | The invoice created on value for this payout invoice |
| `--invoice-currency-code` | string | The invoice currency code value for this payout invoice |
| `--invoice-business-id` | int | ID of the invoice business associated with this record |
| `--from-invoice-business-id` | range | |
| `--to-invoice-business-id` | range | |
| `--invoice-business-name` | string | Display name of the linked invoice business (read-only) |
| `--reseller-payout-id` | long | ID of the reseller payout linked to this record |
| `--amount` | decimal | The amount value for this payout invoice |
| `--from-amount` | range | |
| `--to-amount` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### PayoutInvoice sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### PayoutInvoice create options

| Option | Type | Description |
| --- | --- | --- |

#### PayoutInvoice update options

| Option | Type | Description |
| --- | --- | --- |

<!-- END:GENERATED entity=PayoutInvoices -->
