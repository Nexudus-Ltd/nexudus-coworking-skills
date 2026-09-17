# Invoices

<!-- BEGIN:GENERATED entity=Invoices -->

An Invoice is the PLATFORM bill Nexudus issues to the operator (the business running the coworking space) for their own Nexudus subscription and usage. It is NOT the invoice a location issues to its customers — those are CoworkerInvoice records, served by the coworker_invoice_* tools, and are what an operator means by 'invoice' unless they explicitly say otherwise. Select the invoice_* tools only when the request explicitly names the Nexudus subscription or platform bill (for example 'my Nexudus invoice', 'our subscription invoice', 'what Nexudus charges us'). A customer name, team name or bare invoice number is not such a signal, and the two entities share no records and no numbering sequence. Each platform invoice captures a snapshot of the billing details at issuance time — bill-to address, currency, tax amounts, and line items — and is immutable with respect to those values; later changes to financial accounts, products or operator details do not update existing invoices. Platform invoices support list, get, and create operations. They cannot be updated or deleted through the API.

Invoices support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus invoices list --agent` | List all invoices |
| `nexudus invoices list --id <id> --agent` | Filter by single ID |
| `nexudus invoices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus invoices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus invoices list --invoice-number <value> --bill-to-name <value> --agent` | Filter invoices by properties |
| `nexudus invoices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus invoices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus invoices get <id> --agent` | Get single invoice |
| `nexudus invoices update <id> --name "New Name" --agent` | Update invoice |

#### Invoice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--invoice-number` | string | Unique sequential invoice number assigned at issuance (e.g. INV-00042) |
| `--bill-to-name` | string | Name of the person or organisation being billed, captured at invoice time |
| `--bill-to-address` | string | Billing street address, captured at invoice time |
| `--bill-to-city` | string | Billing city, captured at invoice time |
| `--bill-to-tax-id-number` | string | Tax identification number (VAT/GST/EIN) of the billed party, captured at invoice time |
| `--bill-to-post-code` | string | Billing postal/ZIP code, captured at invoice time |
| `--bill-to-phone` | string | Billing phone number, captured at invoice time |
| `--bill-to-fax` | string | Billing fax number, captured at invoice time |
| `--bill-to-country-id` | long | ID of the bill to country linked to this record |
| `--bill-to-country-name` | string | Display value for BillToCountry.Name. |
| `--description` | string | Free-text description or notes for this invoice |
| `--discount-amount` | decimal | Total discount applied to the invoice, in the invoice currency |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--due-date` | DateTime | Date by which payment is expected |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--invoice-from-date` | DateTime | Start date of the billing period covered by this invoice |
| `--from-invoice-from-date` | range | |
| `--to-invoice-from-date` | range | |
| `--invoice-to-date` | DateTime | End date of the billing period covered by this invoice |
| `--from-invoice-to-date` | range | |
| `--to-invoice-to-date` | range | |
| `--subscription-amount` | decimal | Portion of the total that corresponds to recurring subscription charges |
| `--from-subscription-amount` | range | |
| `--to-subscription-amount` | range | |
| `--reseller-amount` | decimal | Portion of the total attributed to the reseller (partner) channel |
| `--from-reseller-amount` | range | |
| `--to-reseller-amount` | range | |
| `--total-amount` | decimal | Grand total of the invoice including all line items, taxes, and discounts |
| `--from-total-amount` | range | |
| `--to-total-amount` | range | |
| `--currency-id` | long | ID of the currency linked to this record |
| `--currency-code` | string | Display value for Currency.Code. |
| `--tax-amount` | decimal | Total tax amount calculated for the invoice |
| `--from-tax-amount` | range | |
| `--to-tax-amount` | range | |
| `--paid` | bool | Whether the invoice has been fully paid |
| `--paid-on` | DateTime | Date and time when full payment was recorded |
| `--from-paid-on` | range | |
| `--to-paid-on` | range | |
| `--custom-data` | string | Arbitrary JSON or text blob for storing integration-specific metadata |
| `--payment-attempts-count` | int | Number of automatic payment collection attempts made for this invoice |
| `--from-payment-attempts-count` | range | |
| `--to-payment-attempts-count` | range | |
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
