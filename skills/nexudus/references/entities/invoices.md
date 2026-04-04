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
| `nexudus invoices get <id> --agent` | Get single invoice |
| `nexudus invoices update <id> --name "New Name" --agent` | Update invoice |

#### Invoice list filter options

`--business-id`, `--bill-to-name`, `--bill-to-address`, `--bill-to-city`, `--bill-to-tax-id-number`, `--bill-to-post-code`, `--bill-to-phone`, `--bill-to-fax`, `--bill-to-country-id`

#### Invoice update options

`--business-id`, `--bill-to-name`, `--bill-to-address`, `--bill-to-city`, `--bill-to-tax-id-number`, `--bill-to-post-code`, `--bill-to-phone`, `--bill-to-fax`, `--bill-to-country-id`

### Invoice (key fields)

`Id`, `InvoiceNumber`, `BillToName`, `DueDate`, `TotalAmount`, `Paid`

<!-- END:GENERATED entity=Invoices -->
