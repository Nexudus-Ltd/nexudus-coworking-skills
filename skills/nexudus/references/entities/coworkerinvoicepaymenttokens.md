# CoworkerInvoicePaymentTokens

<!-- BEGIN:GENERATED entity=CoworkerInvoicePaymentTokens -->

A **CoworkerInvoicePaymentToken** is an internal record of the token used to process the payment for a customer invoice.

Each token links a `CoworkerInvoice` to the payment provider and the provider-specific token string used to authorise or capture the payment. Use the `Notes` field to store any additional context about the token.

CoworkerInvoicePaymentTokens support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerinvoicepaymenttokens list --agent` | List all coworkerinvoicepaymenttokens |
| `nexudus coworkerinvoicepaymenttokens list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerinvoicepaymenttokens list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerinvoicepaymenttokens list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerinvoicepaymenttokens list --regular-payment-provider <value> --token <value> --agent` | Filter coworkerinvoicepaymenttokens by properties |
| `nexudus coworkerinvoicepaymenttokens list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerinvoicepaymenttokens get <id> --agent` | Get single coworkerinvoicepaymenttoken |
| `nexudus coworkerinvoicepaymenttokens create --coworker-invoice-id <value> --agent` | Create coworkerinvoicepaymenttoken |
| `nexudus coworkerinvoicepaymenttokens update <id> --name "New Name" --agent` | Update coworkerinvoicepaymenttoken |
| `nexudus coworkerinvoicepaymenttokens delete <id> --yes --agent` | Delete coworkerinvoicepaymenttoken (no prompt) |

#### CoworkerInvoicePaymentToken list filter options

`--coworker-invoice-id` (long), `--regular-payment-provider` (enum), `--token`, `--notes`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerInvoicePaymentToken create options

`--coworker-invoice-id` (long, required), `--regular-payment-provider` (enum), `--token`, `--notes`

#### CoworkerInvoicePaymentToken update options

`--coworker-invoice-id` (long), `--regular-payment-provider` (enum), `--token`, `--notes`

### CoworkerInvoicePaymentToken (key fields)

`Id`, `RegularPaymentProvider`, `Token`

<!-- END:GENERATED entity=CoworkerInvoicePaymentTokens -->
