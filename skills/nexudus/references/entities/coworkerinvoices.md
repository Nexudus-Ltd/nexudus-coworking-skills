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

`--coworker-id` (long), `--business-id` (long), `--invoice-number`, `--payment-reference`, `--bill-to-name`, `--bill-to-address`, `--bill-to-city`, `--bill-to-post-code`, `--bill-to-phone`, `--bill-to-fax`, `--bill-to-state`, `--bill-to-country-id` (long), `--bill-to-bank-account`, `--bill-to-tax-id-number`, `--purchase-order`, `--due-date` (DateTime), `--from-due-date` (range), `--to-due-date` (range), `--invoice-from-date` (DateTime), `--from-invoice-from-date` (range), `--to-invoice-from-date` (range), `--invoice-to-date` (DateTime), `--from-invoice-to-date` (range), `--to-invoice-to-date` (range), `--transaction-total-amount` (decimal), `--from-transaction-total-amount` (range), `--to-transaction-total-amount` (range), `--transaction-currency-id` (long), `--transaction-exchange-rate` (decimal), `--from-transaction-exchange-rate` (range), `--to-transaction-exchange-rate` (range), `--currency-id` (long), `--draft` (bool), `--paid-on` (DateTime), `--from-paid-on` (range), `--to-paid-on` (range), `--storecove-invoice-status` (enum), `--billed` (bool), `--do-not-apply-credit-automatically` (bool), `--created-on-local` (DateTime), `--from-created-on-local` (range), `--to-created-on-local` (range), `--due-date-local` (DateTime), `--from-due-date-local` (range), `--to-due-date-local` (range), `--invoice-from-date-local` (DateTime), `--from-invoice-from-date-local` (range), `--to-invoice-from-date-local` (range), `--invoice-to-date-local` (DateTime), `--from-invoice-to-date-local` (range), `--to-invoice-to-date-local` (range), `--paid-on-local` (DateTime), `--from-paid-on-local` (range), `--to-paid-on-local` (range), `--refunded-on-local` (DateTime), `--from-refunded-on-local` (range), `--to-refunded-on-local` (range), `--last-payment-attempt-local` (DateTime), `--from-last-payment-attempt-local` (range), `--to-last-payment-attempt-local` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerInvoice update options

`--coworker-id` (long), `--business-id` (long), `--invoice-number`, `--payment-reference`, `--bill-to-name`, `--bill-to-address`, `--bill-to-city`, `--bill-to-post-code`, `--bill-to-phone`, `--bill-to-fax`, `--bill-to-state`, `--bill-to-country-id` (long), `--bill-to-bank-account`, `--bill-to-tax-id-number`, `--purchase-order`, `--due-date` (DateTime), `--invoice-from-date` (DateTime), `--invoice-to-date` (DateTime), `--transaction-total-amount` (decimal), `--transaction-currency-id` (long), `--transaction-exchange-rate` (decimal), `--currency-id` (long), `--draft` (bool), `--paid-on` (DateTime), `--storecove-invoice-status` (enum), `--billed` (bool), `--do-not-apply-credit-automatically` (bool), `--created-on-local` (DateTime), `--due-date-local` (DateTime), `--invoice-from-date-local` (DateTime), `--invoice-to-date-local` (DateTime), `--paid-on-local` (DateTime), `--refunded-on-local` (DateTime), `--last-payment-attempt-local` (DateTime)

### CoworkerInvoice (key fields)

`Id`, `CoworkerFullName`, `InvoiceNumber`, `BillToName`, `DueDate`, `TotalAmount`, `Draft`, `Paid`

#### CoworkerInvoice enum values

| Option | Valid values |
| ------ | ------------ |
| `--storecove-invoice-status` | `1` None, `2` TransferFailed, `3` Processing, `4` ProcessingFailed, `5` Processed |

<!-- END:GENERATED entity=CoworkerInvoices -->
