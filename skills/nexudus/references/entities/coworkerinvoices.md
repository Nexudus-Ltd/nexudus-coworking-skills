# CoworkerInvoices

<!-- BEGIN:GENERATED entity=CoworkerInvoices -->

CoworkerInvoice records a customer billing document for a location, including charges, payment status, and invoice delivery.

CoworkerInvoices support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus coworkerinvoices list --agent` | List all coworkerinvoices |
| `nexudus coworkerinvoices list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerinvoices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerinvoices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerinvoices list --coworker-full-name <value> --invoice-number <value> --agent` | Filter coworkerinvoices by properties |
| `nexudus coworkerinvoices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerinvoices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerinvoices get <id> --agent` | Get single coworkerinvoice |
| `nexudus coworkerinvoices update <id> --name "New Name" --agent` | Update coworkerinvoice |

#### CoworkerInvoice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer billed by this invoice. |
| `--coworker-full-name` | string | Full name of the invoiced customer |
| `--coworker-regular-payment-contract-number` | string | The coworker regular payment contract number value for this coworker invoice |
| `--coworker-regular-payment-provider` | string | The coworker regular payment provider value for this coworker invoice |
| `--coworker-card-number` | string | The coworker card number value for this coworker invoice |
| `--coworker-go-cardless-contract-number` | string | The coworker go cardless contract number value for this coworker invoice |
| `--coworker-enable-go-cardless-payments` | bool | Whether coworker enable go cardless payments is enabled |
| `--coworker-billing-email` | string | Billing email address of the customer |
| `--coworker-notify-on-new-invoice` | bool | Whether coworker notify on new invoice is enabled |
| `--coworker-notify-on-new-payment` | bool | Whether coworker notify on new payment is enabled |
| `--coworker-notify-on-failed-payment` | bool | Whether coworker notify on failed payment is enabled |
| `--coworker-do-not-process-invoices-automatically` | bool | Whether coworker do not process invoices automatically is enabled |
| `--coworker-company-name` | string | Company name of the invoiced customer |
| `--coworker-team-names` | string | Team names the invoiced customer belongs to |
| `--business-id` | long | ID of the location that owns and issues this invoice. |
| `--business-name` | string | Name of the location that issued the invoice |
| `--invoice-number` | string | Unique invoice number, assigned when the invoice is issued. |
| `--payment-reference` | string | Payment reference used for reconciliation; normally follows the invoice number. |
| `--bill-to-name` | string | Name of the person or organisation billed, captured on the invoice. |
| `--bill-to-address` | string | Billing street address captured on the invoice. |
| `--bill-to-city` | string | Billing city captured on the invoice. |
| `--bill-to-post-code` | string | Billing postal or ZIP code captured on the invoice. |
| `--bill-to-phone` | string | Optional billing phone number captured on the invoice. |
| `--bill-to-fax` | string | Optional billing fax number captured on the invoice. |
| `--bill-to-state` | string | Optional billing state, province, or region captured on the invoice. |
| `--bill-to-country-id` | long | ID of the country in the billing address. |
| `--bill-to-country-name` | string | Name of the billing country on the invoice |
| `--bill-to-country-two-digits-code` | string | The bill to country two digits code value for this coworker invoice |
| `--bill-to-bank-account` | string | Optional bank-account details printed for payment instructions. |
| `--bill-to-tax-id-number` | string | Optional tax identification number of the billed party. |
| `--purchase-order` | string | Optional customer purchase-order reference. |
| `--description` | string | Read-only summary generated from the invoice lines; change lines instead. |
| `--discount-amount` | decimal | Read-only stored invoice-level discount amount in the invoice currency; UpdateTotals does not recalculate it because line SubTotal values already include line discounts. |
| `--from-discount-amount` | range | |
| `--to-discount-amount` | range | |
| `--due-date` | DateTime | Optional payment due date in the location's timezone. When an invoice is created, the system calculates it using the customer's due day or InvoiceDueDatePeriod first, then a due-date term configured for a plan on the invoice's contract lines, the contract-period-start setting, and finally the location default; customer and plan periods are capped at 365 days. If several plan due-date terms apply, it uses the earliest next due date. |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--invoice-from-date` | DateTime | Read-only start of the contract billing period, calculated from the InvoicedPeriod of the contract being invoiced. |
| `--from-invoice-from-date` | range | |
| `--to-invoice-from-date` | range | |
| `--invoice-to-date` | DateTime | Read-only end of the contract billing period, calculated from the billing period of the contract's associated plan. |
| `--from-invoice-to-date` | range | |
| `--to-invoice-to-date` | range | |
| `--total-amount` | decimal | Read-only gross invoice total: sum of every line's SubTotal plus TaxAmount after each line is rounded, then rounded to the location's invoice decimal precision. |
| `--from-total-amount` | range | |
| `--to-total-amount` | range | |
| `--paid-amount` | decimal | Read-only database total of all CoworkerLedgerEntry Credit values linked to this invoice; negative credit entries reduce the amount. |
| `--from-paid-amount` | range | |
| `--to-paid-amount` | range | |
| `--transaction-total-amount` | decimal | Stored total to collect in the payment transaction currency, set to TotalAmount multiplied by Payments.ExchangeRate and rounded to two decimals; the outstanding balance proportionally subtracts net ledger credits. |
| `--from-transaction-total-amount` | range | |
| `--to-transaction-total-amount` | range | |
| `--transaction-currency-id` | long | ID of the currency used to collect payment; defaults to the location's invoice currency unless Payments.Currency specifies a transaction currency. |
| `--transaction-currency-code` | string | The transaction currency code value for this coworker invoice |
| `--transaction-exchange-rate` | decimal | Fixed multiplier from invoice currency to transaction currency, copied from the location's Payments.ExchangeRate setting when invoice totals are updated. |
| `--from-transaction-exchange-rate` | range | |
| `--to-transaction-exchange-rate` | range | |
| `--currency-id` | long | ID of the currency used to state invoice amounts. |
| `--currency-code` | string | ISO currency code (e.g. USD, EUR, GBP) |
| `--tax-amount` | decimal | Read-only tax total: sum of every rounded invoice-line TaxAmount, then rounded to the location's invoice decimal precision. |
| `--from-tax-amount` | range | |
| `--to-tax-amount` | range | |
| `--draft` | bool | Whether this invoice remains a draft rather than a final issued invoice. |
| `--void` | bool | Whether this invoice has been voided or cancelled; voiding deletes all CoworkerLedgerEntry records associated with the invoice. |
| `--waiting-for-invoice-number` | bool | Whether the invoice is awaiting its final sequential number. |
| `--paid` | bool | Whether payments have marked the invoice as paid. |
| `--sent` | bool | Whether the invoice has been sent to the customer. |
| `--sent-on` | DateTime | Read-only date and time when the invoice was sent. |
| `--from-sent-on` | range | |
| `--to-sent-on` | range | |
| `--paid-on` | DateTime | Date and time recorded as paid; it updates payment ledger dates. |
| `--from-paid-on` | range | |
| `--to-paid-on` | range | |
| `--refunded` | bool | Whether all non-zero invoice lines have been refunded. |
| `--xero-invoice-transferred` | bool | Whether the invoice has been transferred to Xero. |
| `--xero-payment-transferred` | bool | Whether invoice payments have been transferred to Xero. |
| `--quickbooks-invoice-transferred` | bool | Whether the invoice has been transferred to QuickBooks. |
| `--quickbooks-payment-transferred` | bool | Whether invoice payments have been transferred to QuickBooks. |
| `--moloni-invoice-transferred` | bool | Whether the invoice has been transferred to Moloni. |
| `--moloni-payment-transferred` | bool | Whether invoice payments have been transferred to Moloni. |
| `--storecove-invoice-status` | enum | Read-only Storecove transfer state: None, TransferFailed, Processing, ProcessingFailed, or Processed. |
| `--auto-transfer-to-storecove` | bool | Whether the invoice is configured for automatic Storecove transfer. |
| `--refunded-on` | DateTime | Read-only date and time when the invoice was refunded. |
| `--from-refunded-on` | range | |
| `--to-refunded-on` | range | |
| `--credit-note` | bool | Whether this invoice is a credit note. |
| `--original-invoice-guid` | string | Read-only unique ID of the original invoice related to this credit note. |
| `--contract-guid` | string | Read-only unique ID of the customer plan contract that generated this invoice. |
| `--last-payment-attempt` | DateTime | Read-only timestamp of the most recent automatic payment attempt. |
| `--from-last-payment-attempt` | range | |
| `--to-last-payment-attempt` | range | |
| `--do-not-apply-credit-automatically` | bool | Whether credit resulting from crediting a paid invoice must not be automatically applied to future invoices; the operator can allocate the credit manually. |
| `--received-amount` | decimal | Read-only database-maintained reporting amount for payments received; it is not calculated by invoice UpdateTotals. |
| `--from-received-amount` | range | |
| `--to-received-amount` | range | |
| `--credited-amount` | decimal | Read-only database-maintained reporting amount for credit applied or issued; it is not calculated by invoice UpdateTotals. |
| `--from-credited-amount` | range | |
| `--to-credited-amount` | range | |
| `--refunded-amount` | decimal | Read-only database-maintained reporting amount for refunds; it is not calculated by invoice UpdateTotals. |
| `--from-refunded-amount` | range | |
| `--to-refunded-amount` | range | |
| `--auto-transfer-to-xero-or-quickbooks` | bool | Whether the invoice is configured for automatic Xero or QuickBooks transfer. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerInvoice sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `InvoiceNumber` ascending. If no `--order-by` is specified, the API returns results ordered by `InvoiceNumber` (ascending).

#### CoworkerInvoice update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer billed by this invoice. |
| `--business-id` | long | ID of the location that owns and issues this invoice. |
| `--invoice-number` | string | Unique invoice number, assigned when the invoice is issued. |
| `--payment-reference` | string | Payment reference used for reconciliation; normally follows the invoice number. |
| `--bill-to-name` | string | Name of the person or organisation billed, captured on the invoice. |
| `--bill-to-address` | string | Billing street address captured on the invoice. |
| `--bill-to-city` | string | Billing city captured on the invoice. |
| `--bill-to-post-code` | string | Billing postal or ZIP code captured on the invoice. |
| `--bill-to-phone` | string | Optional billing phone number captured on the invoice. |
| `--bill-to-fax` | string | Optional billing fax number captured on the invoice. |
| `--bill-to-state` | string | Optional billing state, province, or region captured on the invoice. |
| `--bill-to-country-id` | long | ID of the country in the billing address. |
| `--bill-to-bank-account` | string | Optional bank-account details printed for payment instructions. |
| `--bill-to-tax-id-number` | string | Optional tax identification number of the billed party. |
| `--purchase-order` | string | Optional customer purchase-order reference. |
| `--due-date` | DateTime | Optional payment due date in the location's timezone. When an invoice is created, the system calculates it using the customer's due day or InvoiceDueDatePeriod first, then a due-date term configured for a plan on the invoice's contract lines, the contract-period-start setting, and finally the location default; customer and plan periods are capped at 365 days. If several plan due-date terms apply, it uses the earliest next due date. |
| `--transaction-total-amount` | decimal | Stored total to collect in the payment transaction currency, set to TotalAmount multiplied by Payments.ExchangeRate and rounded to two decimals; the outstanding balance proportionally subtracts net ledger credits. |
| `--transaction-currency-id` | long | ID of the currency used to collect payment; defaults to the location's invoice currency unless Payments.Currency specifies a transaction currency. |
| `--transaction-exchange-rate` | decimal | Fixed multiplier from invoice currency to transaction currency, copied from the location's Payments.ExchangeRate setting when invoice totals are updated. |
| `--currency-id` | long | ID of the currency used to state invoice amounts. |
| `--draft` | bool | Whether this invoice remains a draft rather than a final issued invoice. |
| `--paid-on` | DateTime | Date and time recorded as paid; it updates payment ledger dates. |
| `--storecove-invoice-status` | enum | Read-only Storecove transfer state: None, TransferFailed, Processing, ProcessingFailed, or Processed. |
| `--do-not-apply-credit-automatically` | bool | Whether credit resulting from crediting a paid invoice must not be automatically applied to future invoices; the operator can allocate the credit manually. |

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
