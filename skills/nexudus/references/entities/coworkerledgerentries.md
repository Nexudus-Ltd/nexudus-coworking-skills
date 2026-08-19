# CoworkerLedgerEntries

<!-- BEGIN:GENERATED entity=CoworkerLedgerEntries -->

A CoworkerLedgerEntry, shown as a ledger entry, records a payment, charge, credit, or adjustment in a customer's financial ledger for a location and can be applied to an invoice.

CoworkerLedgerEntries support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerledgerentries list --agent` | List all coworkerledgerentries |
| `nexudus coworkerledgerentries list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerledgerentries list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerledgerentries list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerledgerentries list --coworker-full-name <value> --description <value> --agent` | Filter coworkerledgerentries by properties |
| `nexudus coworkerledgerentries list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerledgerentries list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerledgerentries get <id> --agent` | Get single coworkerledgerentry |
| `nexudus coworkerledgerentries create --business-id <value> --coworker-id <value> --description <value> --code <value> --debit <value> --credit <value> --agent` | Create coworkerledgerentry |
| `nexudus coworkerledgerentries update <id> --name "New Name" --agent` | Update coworkerledgerentry |
| `nexudus coworkerledgerentries delete <id> --yes --agent` | Delete coworkerledgerentry (no prompt) |

#### CoworkerLedgerEntry list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this ledger entry. |
| `--business-name` | string | Location name |
| `--business-currency-code` | string | Location currency code |
| `--coworker-id` | long | ID of the customer whose ledger contains this entry. |
| `--coworker-full-name` | string | Coworker full name |
| `--coworker-invoice-id` | long | Optional ID of the invoice this payment, charge, or credit is applied to. |
| `--invoice-number` | string | Invoice number |
| `--invoice-total-amount` | decimal | Invoice total amount |
| `--from-invoice-total-amount` | range | |
| `--to-invoice-total-amount` | range | |
| `--coworker-invoice-bill-to-name` | string | Invoice bill-to name |
| `--coworker-invoice-paid` | bool | Whether the invoice has been paid |
| `--coworker-invoice-paid-on` | DateTime | Date the invoice was paid |
| `--from-coworker-invoice-paid-on` | range | |
| `--to-coworker-invoice-paid-on` | range | |
| `--coworker-invoice-refunded` | bool | Whether the invoice has been refunded |
| `--coworker-invoice-refunded-on` | DateTime | Date the invoice was refunded |
| `--from-coworker-invoice-refunded-on` | range | |
| `--to-coworker-invoice-refunded-on` | range | |
| `--coworker-invoice-due-date` | DateTime | Invoice due date |
| `--from-coworker-invoice-due-date` | range | |
| `--to-coworker-invoice-due-date` | range | |
| `--coworker-invoice-draft` | bool | Whether the invoice is a draft |
| `--coworker-invoice-waiting-for-invoice-number` | bool | Whether the invoice is waiting to be assigned an invoice number |
| `--description` | string | Required free-text explanation of the payment, charge, credit, or adjustment. |
| `--code` | string | Required ledger reference code; payment and invoice workflows commonly generate codes such as PAYM-, CASH-, CRED-, REFD-, or INVC-. |
| `--debit` | decimal | Debit amount in the location currency, rounded to two decimal places when saved; positive debits are invoice charges and negative debits are credit notes. Debit and Credit are mutually exclusive, so set the other amount to zero. |
| `--from-debit` | range | |
| `--to-debit` | range | |
| `--credit` | decimal | Credit amount in the location currency, rounded to two decimal places when saved; positive credits are received payments and negative credits are refunded payments. Credit and Debit are mutually exclusive, so set the other amount to zero. |
| `--from-credit` | range | |
| `--to-credit` | range | |
| `--payment-gateway-name` | enum | Payment provider or payment method for this transaction; choosing a connected gateway such as Stripe or Spreedly attempts to collect payment and creation can fail if collection fails. Manual payments cannot use GoCardless, GoCardlessPro, StripeDirectDebit, Xero, Forte, or StripeACH. |
| `--transaction-date` | DateTime | Date and time of the transaction in UTC; defaults to the current UTC time when omitted and cannot be before the location billing lock date. |
| `--from-transaction-date` | range | |
| `--to-transaction-date` | range | |
| `--balance` | decimal | Read-only running ledger balance calculated by the database as cumulative credits minus debits, ordered by transaction date and entry ID. |
| `--from-balance` | range | |
| `--to-balance` | range | |
| `--connected-transaction-guid` | string | Internal identifier linking related ledger transactions so that deletion can reverse the connected payment; hidden because it is managed by payment workflows. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerLedgerEntry sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `TransactionDate` ascending. If no `--order-by` is specified, the API returns results ordered by `TransactionDate` (ascending).

#### CoworkerLedgerEntry create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this ledger entry. |
| `--coworker-id` | long, required | ID of the customer whose ledger contains this entry. |
| `--coworker-invoice-id` | long | Optional ID of the invoice this payment, charge, or credit is applied to. |
| `--description` | string, required | Required free-text explanation of the payment, charge, credit, or adjustment. |
| `--code` | string, required | Required ledger reference code; payment and invoice workflows commonly generate codes such as PAYM-, CASH-, CRED-, REFD-, or INVC-. |
| `--debit` | decimal, required | Debit amount in the location currency, rounded to two decimal places when saved; positive debits are invoice charges and negative debits are credit notes. Debit and Credit are mutually exclusive, so set the other amount to zero. |
| `--credit` | decimal, required | Credit amount in the location currency, rounded to two decimal places when saved; positive credits are received payments and negative credits are refunded payments. Credit and Debit are mutually exclusive, so set the other amount to zero. |
| `--payment-gateway-name` | enum | Payment provider or payment method for this transaction; choosing a connected gateway such as Stripe or Spreedly attempts to collect payment and creation can fail if collection fails. Manual payments cannot use GoCardless, GoCardlessPro, StripeDirectDebit, Xero, Forte, or StripeACH. |
| `--transaction-date` | DateTime | Date and time of the transaction in UTC; defaults to the current UTC time when omitted and cannot be before the location billing lock date. |
| `--connected-transaction-guid` | string | Internal identifier linking related ledger transactions so that deletion can reverse the connected payment; hidden because it is managed by payment workflows. |

#### CoworkerLedgerEntry update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this ledger entry. |
| `--coworker-id` | long | ID of the customer whose ledger contains this entry. |
| `--coworker-invoice-id` | long | Optional ID of the invoice this payment, charge, or credit is applied to. |
| `--description` | string | Required free-text explanation of the payment, charge, credit, or adjustment. |
| `--code` | string | Required ledger reference code; payment and invoice workflows commonly generate codes such as PAYM-, CASH-, CRED-, REFD-, or INVC-. |
| `--debit` | decimal | Debit amount in the location currency, rounded to two decimal places when saved; positive debits are invoice charges and negative debits are credit notes. Debit and Credit are mutually exclusive, so set the other amount to zero. |
| `--credit` | decimal | Credit amount in the location currency, rounded to two decimal places when saved; positive credits are received payments and negative credits are refunded payments. Credit and Debit are mutually exclusive, so set the other amount to zero. |
| `--transaction-date` | DateTime | Date and time of the transaction in UTC; defaults to the current UTC time when omitted and cannot be before the location billing lock date. |
| `--connected-transaction-guid` | string | Internal identifier linking related ledger transactions so that deletion can reverse the connected payment; hidden because it is managed by payment workflows. |

#### CoworkerLedgerEntry PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkerledgerentries update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerLedgerEntry (key fields)

`Id`, `CoworkerFullName`, `Description`, `Code`, `Debit`, `Credit`

<!-- END:GENERATED entity=CoworkerLedgerEntries -->
