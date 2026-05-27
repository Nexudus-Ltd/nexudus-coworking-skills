# CoworkerInvoices

<!-- BEGIN:GENERATED entity=CoworkerInvoices -->

A **CoworkerInvoice** represents an invoice document issued to a customer. Invoices track amounts owed, payment status, billing details, and integration state with external accounting systems.

Invoices can be in draft or final state. A draft invoice (`--draft true`) can still be modified before being finalised. Once finalised, an invoice number is assigned and the invoice can be sent to the customer.

An invoice may also be a **credit note** (`--credit-note true`), which references the original invoice via `--original-invoice-guid` and represents a reversal or adjustment.

Payment status is tracked via `--paid`, `--paid-amount`, and `--paid-on`. Partial payments are possible — compare `PaidAmount` against `TotalAmount` to determine outstanding balance. Refunds are tracked separately via `--refunded`, `--refunded-on`, and `--refunded-amount`.

CoworkerInvoices support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkerinvoices list --agent` | List all coworkerinvoices |
| `nexudus coworkerinvoices list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerinvoices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerinvoices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerinvoices list --invoice-number <value> --bill-to-name <value> --agent` | Filter coworkerinvoices by properties |
| `nexudus coworkerinvoices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerinvoices get <id> --agent` | Get single coworkerinvoice |
| `nexudus coworkerinvoices update <id> --name "New Name" --agent` | Update coworkerinvoice |

#### CoworkerInvoice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--invoice-number` | string | Unique invoice number assigned when the invoice is finalised |
| `--payment-reference` | string | Reference code used to match payments to this invoice |
| `--bill-to-name` | string | Name of the person or company being billed |
| `--bill-to-address` | string | Billing address on the invoice |
| `--bill-to-city` | string | Billing city on the invoice |
| `--bill-to-post-code` | string | Billing post code on the invoice |
| `--bill-to-phone` | string | Billing phone number on the invoice |
| `--bill-to-fax` | string | Billing fax number on the invoice |
| `--bill-to-state` | string | Billing state or region on the invoice |
| `--bill-to-country-id` | long | ID of the bill to country linked to this record |
| `--bill-to-bank-account` | string | Bank account number on the invoice for payment |
| `--bill-to-tax-id-number` | string | Tax identification number of the billed party |
| `--purchase-order` | string | Customer purchase order number for this invoice |
| `--due-date` | DateTime | Date by which payment is due |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--invoice-from-date` | DateTime | Start date of the billing period covered by this invoice |
| `--from-invoice-from-date` | range | |
| `--to-invoice-from-date` | range | |
| `--invoice-to-date` | DateTime | End date of the billing period covered by this invoice |
| `--from-invoice-to-date` | range | |
| `--to-invoice-to-date` | range | |
| `--transaction-total-amount` | decimal | The transaction total amount value for this coworker invoice |
| `--from-transaction-total-amount` | range | |
| `--to-transaction-total-amount` | range | |
| `--transaction-currency-id` | long | ID of the transaction currency linked to this record |
| `--transaction-exchange-rate` | decimal | The transaction exchange rate value for this coworker invoice |
| `--from-transaction-exchange-rate` | range | |
| `--to-transaction-exchange-rate` | range | |
| `--currency-id` | long | ID of the currency linked to this record |
| `--draft` | bool | Whether the invoice is still a draft. Draft invoices can be modified before finalisation |
| `--paid-on` | DateTime | Date the invoice was marked as fully paid |
| `--from-paid-on` | range | |
| `--to-paid-on` | range | |
| `--storecove-invoice-status` | enum | Status of e-invoicing transfer via Storecove |
| `--billed` | bool | Whether billed is enabled |
| `--do-not-apply-credit-automatically` | bool | Whether to skip automatic application of available credit to this invoice |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--from-created-on-local` | range | |
| `--to-created-on-local` | range | |
| `--due-date-local` | DateTime | Date/time value for due date local |
| `--from-due-date-local` | range | |
| `--to-due-date-local` | range | |
| `--invoice-from-date-local` | DateTime | Date/time value for invoice from date local |
| `--from-invoice-from-date-local` | range | |
| `--to-invoice-from-date-local` | range | |
| `--invoice-to-date-local` | DateTime | Date/time value for invoice to date local |
| `--from-invoice-to-date-local` | range | |
| `--to-invoice-to-date-local` | range | |
| `--paid-on-local` | DateTime | Date/time value for paid on local |
| `--from-paid-on-local` | range | |
| `--to-paid-on-local` | range | |
| `--refunded-on-local` | DateTime | Date/time value for refunded on local |
| `--from-refunded-on-local` | range | |
| `--to-refunded-on-local` | range | |
| `--last-payment-attempt-local` | DateTime | Date/time value for last payment attempt local |
| `--from-last-payment-attempt-local` | range | |
| `--to-last-payment-attempt-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerInvoice update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--invoice-number` | string | Unique invoice number assigned when the invoice is finalised |
| `--payment-reference` | string | Reference code used to match payments to this invoice |
| `--bill-to-name` | string | Name of the person or company being billed |
| `--bill-to-address` | string | Billing address on the invoice |
| `--bill-to-city` | string | Billing city on the invoice |
| `--bill-to-post-code` | string | Billing post code on the invoice |
| `--bill-to-phone` | string | Billing phone number on the invoice |
| `--bill-to-fax` | string | Billing fax number on the invoice |
| `--bill-to-state` | string | Billing state or region on the invoice |
| `--bill-to-country-id` | long | ID of the bill to country linked to this record |
| `--bill-to-bank-account` | string | Bank account number on the invoice for payment |
| `--bill-to-tax-id-number` | string | Tax identification number of the billed party |
| `--purchase-order` | string | Customer purchase order number for this invoice |
| `--due-date` | DateTime | Date by which payment is due |
| `--invoice-from-date` | DateTime | Start date of the billing period covered by this invoice |
| `--invoice-to-date` | DateTime | End date of the billing period covered by this invoice |
| `--transaction-total-amount` | decimal | The transaction total amount value for this coworker invoice |
| `--transaction-currency-id` | long | ID of the transaction currency linked to this record |
| `--transaction-exchange-rate` | decimal | The transaction exchange rate value for this coworker invoice |
| `--currency-id` | long | ID of the currency linked to this record |
| `--draft` | bool | Whether the invoice is still a draft. Draft invoices can be modified before finalisation |
| `--paid-on` | DateTime | Date the invoice was marked as fully paid |
| `--storecove-invoice-status` | enum | Status of e-invoicing transfer via Storecove |
| `--billed` | bool | Whether billed is enabled |
| `--do-not-apply-credit-automatically` | bool | Whether to skip automatic application of available credit to this invoice |
| `--created-on-local` | DateTime | Date/time value for created on local |
| `--due-date-local` | DateTime | Date/time value for due date local |
| `--invoice-from-date-local` | DateTime | Date/time value for invoice from date local |
| `--invoice-to-date-local` | DateTime | Date/time value for invoice to date local |
| `--paid-on-local` | DateTime | Date/time value for paid on local |
| `--refunded-on-local` | DateTime | Date/time value for refunded on local |
| `--last-payment-attempt-local` | DateTime | Date/time value for last payment attempt local |

#### CoworkerInvoice PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--bill-to-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--bill-to-address` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--bill-to-city` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--bill-to-post-code` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |

Example:

`nexudus coworkerinvoices update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerInvoice (key fields)

`Id`, `CoworkerFullName`, `InvoiceNumber`, `BillToName`, `DueDate`, `TotalAmount`, `Draft`, `Paid`

#### CoworkerInvoice enum values

| Option | Valid values |
| ------ | ------------ |
| `--storecove-invoice-status` | `1` None, `2` TransferFailed, `3` Processing, `4` ProcessingFailed, `5` Processed |

<!-- END:GENERATED entity=CoworkerInvoices -->
