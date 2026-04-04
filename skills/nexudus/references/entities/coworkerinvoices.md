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

`--coworker-id`, `--business-id`, `--invoice-number`, `--payment-reference`, `--bill-to-name`, `--bill-to-address`, `--bill-to-city`, `--bill-to-post-code`, `--bill-to-phone`, `--bill-to-fax`, `--bill-to-state`, `--bill-to-country-id`, `--bill-to-bank-account`, `--bill-to-tax-id-number`, `--purchase-order`, `--due-date`, `--invoice-from-date`, `--invoice-to-date`, `--transaction-total-amount`, `--transaction-currency-id`, `--transaction-exchange-rate`, `--currency-id`, `--draft`, `--paid-on`, `--storecove-invoice-status`, `--billed`, `--do-not-apply-credit-automatically`, `--created-on-local`, `--due-date-local`, `--invoice-from-date-local`, `--invoice-to-date-local`, `--paid-on-local`, `--refunded-on-local`, `--last-payment-attempt-local`

#### CoworkerInvoice update options

`--coworker-id`, `--business-id`, `--invoice-number`, `--payment-reference`, `--bill-to-name`, `--bill-to-address`, `--bill-to-city`, `--bill-to-post-code`, `--bill-to-phone`, `--bill-to-fax`, `--bill-to-state`, `--bill-to-country-id`, `--bill-to-bank-account`, `--bill-to-tax-id-number`, `--purchase-order`, `--due-date`, `--invoice-from-date`, `--invoice-to-date`, `--transaction-total-amount`, `--transaction-currency-id`, `--transaction-exchange-rate`, `--currency-id`, `--draft`, `--paid-on`, `--storecove-invoice-status`, `--lines` (list, repeat flag), `--added-lines` (list, repeat flag), `--removed-lines` (list, repeat flag), `--payments` (list, repeat flag), `--added-payments` (list, repeat flag), `--removed-payments` (list, repeat flag), `--history` (list, repeat flag), `--added-history` (list, repeat flag), `--removed-history` (list, repeat flag), `--payment-tokens` (list, repeat flag), `--added-payment-tokens` (list, repeat flag), `--removed-payment-tokens` (list, repeat flag), `--billed`, `--do-not-apply-credit-automatically`, `--created-on-local`, `--due-date-local`, `--invoice-from-date-local`, `--invoice-to-date-local`, `--paid-on-local`, `--refunded-on-local`, `--last-payment-attempt-local`

### CoworkerInvoice (key fields)

`Id`, `CoworkerFullName`, `InvoiceNumber`, `BillToName`, `DueDate`, `TotalAmount`, `Draft`, `Paid`

**List properties (only returned by `get`, not by `list`):** `Lines`, `AddedLines`, `RemovedLines`, `Payments`, `AddedPayments`, `RemovedPayments`, `History`, `AddedHistory`, `RemovedHistory`, `PaymentTokens`, `AddedPaymentTokens`, `RemovedPaymentTokens`

#### CoworkerInvoice enum values

| Option | Valid values |
| ------ | ------------ |
| `--storecove-invoice-status` | `1` None, `2` TransferFailed, `3` Processing, `4` ProcessingFailed, `5` Processed |

<!-- END:GENERATED entity=CoworkerInvoices -->
