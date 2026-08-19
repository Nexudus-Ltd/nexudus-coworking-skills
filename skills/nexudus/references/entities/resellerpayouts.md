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
| `nexudus resellerpayouts list --reseller-id <value> --reseller-user-id <value> --agent` | Filter resellerpayouts by properties |
| `nexudus resellerpayouts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resellerpayouts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus resellerpayouts get <id> --agent` | Get single resellerpayout |
| `nexudus resellerpayouts create  --agent` | Create resellerpayout |
| `nexudus resellerpayouts update <id> --name "New Name" --agent` | Update resellerpayout |
| `nexudus resellerpayouts delete <id> --yes --agent` | Delete resellerpayout (no prompt) |

#### ResellerPayout list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--reseller-id` | long | ID of the reseller linked to this record |
| `--reseller-user-id` | int | ID of the reseller user associated with this record |
| `--from-reseller-user-id` | range | |
| `--to-reseller-user-id` | range | |
| `--reseller-user-full-name` | string | Display name of the linked reseller user full (read-only) |
| `--reseller-currency-id` | int | ID of the reseller currency associated with this record |
| `--from-reseller-currency-id` | range | |
| `--to-reseller-currency-id` | range | |
| `--reseller-currency-code` | string | The reseller currency code value for this reseller payout |
| `--approved` | bool | Whether approved is enabled |
| `--paid-out` | bool | Whether paid out is enabled |
| `--paid-out-date` | DateTime | Date/time value for paid out date |
| `--from-paid-out-date` | range | |
| `--to-paid-out-date` | range | |
| `--paid-out-reference` | string | The paid out reference value for this reseller payout |
| `--amount` | decimal | The amount value for this reseller payout |
| `--from-amount` | range | |
| `--to-amount` | range | |
| `--error-description` | string | The error description value for this reseller payout |
| `--last-payment-attempt` | DateTime | Date/time value for last payment attempt |
| `--from-last-payment-attempt` | range | |
| `--to-last-payment-attempt` | range | |
| `--reseller-invoice-data-file-name` | string | Current file name of the reseller invoice data (read-only; upload via the corresponding URL field) |
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
