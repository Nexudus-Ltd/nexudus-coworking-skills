# CoworkerPaymentMethods

<!-- BEGIN:GENERATED entity=CoworkerPaymentMethods -->

A customer payment method (CoworkerPaymentMethod) records the provider credentials used to charge a specific customer at a specific location; only one record is allowed for each customer, location, and provider.

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
| `--coworker-id` | long | ID of the customer whose payment method is stored; the customer must belong to a location the operator can access |
| `--business-id` | long | ID of the location that uses this payment method when charging the customer |
| `--regular-payment-provider` | enum | Regular-payment provider for this method; only one method may exist for the same customer, location, and provider, and the Admin UI supports Stripe, StripeACH, StripeBACS, and GoCardless |
| `--method-id` | string | Payment-provider method ID supplied by the provider, such as a Stripe payment method token; set it only for the matching provider flow |
| `--customer-id` | string | Payment-provider customer ID supplied by the provider, such as a Stripe customer ID; set it only for the matching provider flow |
| `--mandate-id` | string | Payment-provider mandate or bank-account identifier supplied by a direct-debit provider; GoCardless and StripeBACS use this field |
| `--notes` | string | Optional internal notes about this customer payment method |
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
| `--coworker-id` | long, required | ID of the customer whose payment method is stored; the customer must belong to a location the operator can access |
| `--business-id` | long, required | ID of the location that uses this payment method when charging the customer |
| `--regular-payment-provider` | enum | Regular-payment provider for this method; only one method may exist for the same customer, location, and provider, and the Admin UI supports Stripe, StripeACH, StripeBACS, and GoCardless |
| `--method-id` | string | Payment-provider method ID supplied by the provider, such as a Stripe payment method token; set it only for the matching provider flow |
| `--customer-id` | string | Payment-provider customer ID supplied by the provider, such as a Stripe customer ID; set it only for the matching provider flow |
| `--mandate-id` | string | Payment-provider mandate or bank-account identifier supplied by a direct-debit provider; GoCardless and StripeBACS use this field |
| `--notes` | string | Optional internal notes about this customer payment method |

#### CoworkerPaymentMethod update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer whose payment method is stored; the customer must belong to a location the operator can access |
| `--business-id` | long | ID of the location that uses this payment method when charging the customer |
| `--method-id` | string | Payment-provider method ID supplied by the provider, such as a Stripe payment method token; set it only for the matching provider flow |
| `--customer-id` | string | Payment-provider customer ID supplied by the provider, such as a Stripe customer ID; set it only for the matching provider flow |
| `--mandate-id` | string | Payment-provider mandate or bank-account identifier supplied by a direct-debit provider; GoCardless and StripeBACS use this field |
| `--notes` | string | Optional internal notes about this customer payment method |

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
