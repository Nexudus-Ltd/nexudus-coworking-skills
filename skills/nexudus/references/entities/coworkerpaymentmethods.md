# CoworkerPaymentMethods

<!-- BEGIN:GENERATED entity=CoworkerPaymentMethods -->

A **CoworkerPaymentMethod** is a tokenised payment method stored against a customer and a location, used when charging invoices issued to that customer by that location.

Currently supported providers are **Stripe** (card and ACH/BACS) and **GoCardless** (direct debit mandates). The `RegularPaymentProvider` field identifies the provider; valid values for this entity are `Stripe` (2), `StripeACH` (11), `StripeBACS` (13), and `GoCardless` (12).

- For Stripe methods, `MethodId` holds the Stripe payment method ID and `CustomerId` holds the Stripe customer ID.
- For GoCardless mandates, `MandateId` holds the GoCardless mandate ID and `CustomerId` holds the GoCardless customer ID.
- `CardNumber` stores a masked card number for display purposes only.

CoworkerPaymentMethods support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerpaymentmethods list --agent` | List all coworkerpaymentmethods |
| `nexudus coworkerpaymentmethods list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerpaymentmethods list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerpaymentmethods list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerpaymentmethods list --coworker-id <value> --business-id <value> --agent` | Filter coworkerpaymentmethods by properties |
| `nexudus coworkerpaymentmethods list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerpaymentmethods list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerpaymentmethods get <id> --agent` | Get single coworkerpaymentmethod |
| `nexudus coworkerpaymentmethods create --coworker-id <value> --business-id <value> --agent` | Create coworkerpaymentmethod |
| `nexudus coworkerpaymentmethods update <id> --name "New Name" --agent` | Update coworkerpaymentmethod |
| `nexudus coworkerpaymentmethods delete <id> --yes --agent` | Delete coworkerpaymentmethod (no prompt) |

#### CoworkerPaymentMethod list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | Customer this payment method belongs to |
| `--business-id` | long | Location that issued or will charge invoices using this payment method |
| `--regular-payment-provider` | enum | Payment provider for this method. For this entity, valid values are Stripe (2), StripeACH (11), StripeBACS (13), and GoCardless (12). |
| `--method-id` | string | Provider payment method ID (e.g. Stripe payment method ID) |
| `--customer-id` | string | Provider customer ID (e.g. Stripe or GoCardless customer ID) |
| `--mandate-id` | string | GoCardless mandate ID. Only populated for GoCardless payment methods. |
| `--card-number` | string | Masked card number for display purposes only |
| `--notes` | string | Optional notes about this payment method |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerPaymentMethod sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerPaymentMethod create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | Customer this payment method belongs to |
| `--business-id` | long, required | Location that issued or will charge invoices using this payment method |
| `--regular-payment-provider` | enum | Payment provider for this method. For this entity, valid values are Stripe (2), StripeACH (11), StripeBACS (13), and GoCardless (12). |
| `--method-id` | string | Provider payment method ID (e.g. Stripe payment method ID) |
| `--customer-id` | string | Provider customer ID (e.g. Stripe or GoCardless customer ID) |
| `--mandate-id` | string | GoCardless mandate ID. Only populated for GoCardless payment methods. |
| `--card-number` | string | Masked card number for display purposes only |
| `--notes` | string | Optional notes about this payment method |

#### CoworkerPaymentMethod update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | Customer this payment method belongs to |
| `--business-id` | long | Location that issued or will charge invoices using this payment method |
| `--regular-payment-provider` | enum | Payment provider for this method. For this entity, valid values are Stripe (2), StripeACH (11), StripeBACS (13), and GoCardless (12). |
| `--method-id` | string | Provider payment method ID (e.g. Stripe payment method ID) |
| `--customer-id` | string | Provider customer ID (e.g. Stripe or GoCardless customer ID) |
| `--mandate-id` | string | GoCardless mandate ID. Only populated for GoCardless payment methods. |
| `--card-number` | string | Masked card number for display purposes only |
| `--notes` | string | Optional notes about this payment method |

#### CoworkerPaymentMethod PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--card-number` | `FINANCIAL` | `«PII:FINANCIAL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerpaymentmethods update <id> --card-number "«PII:FINANCIAL:a3f2b1c9»" --agent`

### CoworkerPaymentMethod (key fields)

`Id`, `BusinessName`

<!-- END:GENERATED entity=CoworkerPaymentMethods -->
