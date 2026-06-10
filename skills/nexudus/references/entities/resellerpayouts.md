# ResellerPayouts

<!-- BEGIN:GENERATED entity=ResellerPayouts -->

A **ResellerPayout** records a payment made to or received from a reseller partner, tracking payout amounts, dates, and associated invoices.

ResellerPayouts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resellerpayouts list --agent` | List all resellerpayouts |
| `nexudus resellerpayouts list --id <id> --agent` | Filter by single ID |
| `nexudus resellerpayouts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resellerpayouts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resellerpayouts list --new-reseller-invoice-data-url <value> --clear-reseller-invoice-data-file <value> --agent` | Filter resellerpayouts by properties |
| `nexudus resellerpayouts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resellerpayouts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus resellerpayouts get <id> --agent` | Get single resellerpayout |
| `nexudus resellerpayouts create  --agent` | Create resellerpayout |
| `nexudus resellerpayouts update <id> --name "New Name" --agent` | Update resellerpayout |
| `nexudus resellerpayouts delete <id> --yes --agent` | Delete resellerpayout (no prompt) |

#### ResellerPayout list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--new-reseller-invoice-data-url` | string | URL of a new file to upload as the reseller invoice data |
| `--clear-reseller-invoice-data-file` | bool | Set to true to remove the current reseller invoice data file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResellerPayout sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ResellerPayout create options

| Option | Type | Description |
| --- | --- | --- |
| `--new-reseller-invoice-data-url` | string | URL of a new file to upload as the reseller invoice data |
| `--clear-reseller-invoice-data-file` | bool | Set to true to remove the current reseller invoice data file |

#### ResellerPayout update options

| Option | Type | Description |
| --- | --- | --- |
| `--new-reseller-invoice-data-url` | string | URL of a new file to upload as the reseller invoice data |
| `--clear-reseller-invoice-data-file` | bool | Set to true to remove the current reseller invoice data file |

#### ResellerPayout PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--reseller-user-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus resellerpayouts update <id> --reseller-user-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=ResellerPayouts -->
