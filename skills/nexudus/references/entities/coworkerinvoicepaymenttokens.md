# CoworkerInvoicePaymentTokens

<!-- BEGIN:GENERATED entity=CoworkerInvoicePaymentTokens -->

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

`--coworker-invoice-id`, `--regular-payment-provider`, `--token`, `--notes`

#### CoworkerInvoicePaymentToken create options

`--coworker-invoice-id` (required), `--regular-payment-provider`, `--token`, `--notes`

#### CoworkerInvoicePaymentToken update options

`--coworker-invoice-id`, `--regular-payment-provider`, `--token`, `--notes`

### CoworkerInvoicePaymentToken (key fields)

`Id`, `RegularPaymentProvider`, `Token`

<!-- END:GENERATED entity=CoworkerInvoicePaymentTokens -->
