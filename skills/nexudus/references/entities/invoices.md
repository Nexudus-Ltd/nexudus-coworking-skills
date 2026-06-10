# Invoices

<!-- BEGIN:GENERATED entity=Invoices -->

An **Invoice** represents a bill issued by Nexudus to the operator (the business running the coworking space). Invoices are generated automatically by the billing engine or can be created manually via the API.

Each invoice captures a snapshot of the billing details at issuance time — bill-to address, currency, tax amounts, and line items. Once issued, the invoice record is immutable with respect to these captured values; changes to the underlying financial accounts, products or customer details do not retroactively update existing invoices.

Invoices support `list`, `get`, and `create` operations. They cannot be updated or deleted through the API.

Invoices support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus invoices list --agent` | List all invoices |
| `nexudus invoices list --id <id> --agent` | Filter by single ID |
| `nexudus invoices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus invoices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus invoices list --bill-to-name <value> --agent` | Filter invoices by properties |
| `nexudus invoices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus invoices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus invoices get <id> --agent` | Get single invoice |
| `nexudus invoices update <id> --name "New Name" --agent` | Update invoice |

#### Invoice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--bill-to-name` | string | Name of the person or organisation being billed, captured at invoice time |
| `--bill-to-address` | string | Billing street address, captured at invoice time |
| `--bill-to-city` | string | Billing city, captured at invoice time |
| `--bill-to-tax-id-number` | string | Tax identification number (VAT/GST/EIN) of the billed party, captured at invoice time |
| `--bill-to-post-code` | string | Billing postal/ZIP code, captured at invoice time |
| `--bill-to-phone` | string | Billing phone number, captured at invoice time |
| `--bill-to-fax` | string | Billing fax number, captured at invoice time |
| `--bill-to-country-id` | long | ID of the bill to country linked to this record |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Invoice sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Invoice update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--bill-to-name` | string | Name of the person or organisation being billed, captured at invoice time |
| `--bill-to-address` | string | Billing street address, captured at invoice time |
| `--bill-to-city` | string | Billing city, captured at invoice time |
| `--bill-to-tax-id-number` | string | Tax identification number (VAT/GST/EIN) of the billed party, captured at invoice time |
| `--bill-to-post-code` | string | Billing postal/ZIP code, captured at invoice time |
| `--bill-to-phone` | string | Billing phone number, captured at invoice time |
| `--bill-to-fax` | string | Billing fax number, captured at invoice time |
| `--bill-to-country-id` | long | ID of the bill to country linked to this record |

#### Invoice PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--bill-to-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--bill-to-address` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--bill-to-city` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--bill-to-post-code` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |

Example:

`nexudus invoices update <id> --bill-to-name "«PII:NAME:a3f2b1c9»" --agent`

### Invoice (key fields)

`Id`, `InvoiceNumber`, `BillToName`, `DueDate`, `TotalAmount`, `Paid`

<!-- END:GENERATED entity=Invoices -->
