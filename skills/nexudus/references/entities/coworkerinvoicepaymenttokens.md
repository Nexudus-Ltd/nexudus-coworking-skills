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
| `nexudus coworkerinvoicepaymenttokens list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerinvoicepaymenttokens get <id> --agent` | Get single coworkerinvoicepaymenttoken |
| `nexudus coworkerinvoicepaymenttokens create --coworker-invoice-id <value> --agent` | Create coworkerinvoicepaymenttoken |
| `nexudus coworkerinvoicepaymenttokens update <id> --name "New Name" --agent` | Update coworkerinvoicepaymenttoken |
| `nexudus coworkerinvoicepaymenttokens delete <id> --yes --agent` | Delete coworkerinvoicepaymenttoken (no prompt) |

#### CoworkerInvoicePaymentToken list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the coworker invoice linked to this record |
| `--regular-payment-provider` | enum | Payment provider used to process the invoice |
| `--token` | string | Provider-specific token used to authorise or capture the payment |
| `--notes` | string | Additional notes about the payment token |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerInvoicePaymentToken sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerInvoicePaymentToken create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long, required | ID of the coworker invoice linked to this record |
| `--regular-payment-provider` | enum | Payment provider used to process the invoice |
| `--token` | string | Provider-specific token used to authorise or capture the payment |
| `--notes` | string | Additional notes about the payment token |

#### CoworkerInvoicePaymentToken update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-invoice-id` | long | ID of the coworker invoice linked to this record |
| `--regular-payment-provider` | enum | Payment provider used to process the invoice |
| `--token` | string | Provider-specific token used to authorise or capture the payment |
| `--notes` | string | Additional notes about the payment token |

#### CoworkerInvoicePaymentToken PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerinvoicepaymenttokens update <id> --notes "«PII:BIO:a3f2b1c9»" --agent`

### CoworkerInvoicePaymentToken (key fields)

`Id`, `RegularPaymentProvider`, `Token`

<!-- END:GENERATED entity=CoworkerInvoicePaymentTokens -->
