# ContractProducts

<!-- BEGIN:GENERATED entity=ContractProducts -->

A contract product (internally known as ContractProduct) is a recurring product line on a customer's contract, billed with plan invoices and optionally controlled by a price override and billing window. When the product includes passes, booking time credit, monetary credit, or printing credit, those benefits are released as each contract invoice is created; configure the product's credit expiration separately, either aligned with or independent of the billing cycle. A negative product price creates a discount shown as a negative invoice line; use ContractSchedule for a future contract price change instead. Do not use a contract product for a deposit: use ContractDeposit so it is invoiced only at contract start and can be refunded when appropriate.

ContractProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractproducts list --agent` | List all contractproducts |
| `nexudus contractproducts list --id <id> --agent` | Filter by single ID |
| `nexudus contractproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractproducts list --quantity <value> --price <value> --agent` | Filter contractproducts by properties |
| `nexudus contractproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractproducts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus contractproducts get <id> --agent` | Get single contractproduct |
| `nexudus contractproducts create --coworker-contract-id <value> --product-id <value> --quantity <value> --agent` | Create contractproduct |
| `nexudus contractproducts update <id> --name "New Name" --agent` | Update contractproduct |
| `nexudus contractproducts delete <id> --yes --agent` | Delete contractproduct (no prompt) |

#### ContractProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the customer's contract; it determines the location and billing cycle that will receive this recurring product line. |
| `--product-id` | long | ID of the location product billed on the contract's invoices; its current price is used when this line has no price override. |
| `--notes` | string | Optional operator notes about this recurring product line. |
| `--quantity` | int | Number of product units billed in each contract billing cycle; must be at least 1. |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--price` | decimal | Optional per-unit price override in the location's currency; when null, the linked product's price is used. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--repeat-from` | DateTime | Optional UTC date and time for the first invoice period that includes this product line; inclusive, and null starts billing immediately. |
| `--from-repeat-from` | range | |
| `--to-repeat-from` | range | |
| `--repeat-until` | DateTime | Optional UTC date and time for the first invoice period that excludes this product line; exclusive, and null continues billing indefinitely. |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--apply-pro-rating` | bool | Whether this line requests prorating when it ends during an invoice period; the product's setting can also enable prorating, and the contract plan must have ProrateDaysBefore configured. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractProduct sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ContractProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long, required | ID of the customer's contract; it determines the location and billing cycle that will receive this recurring product line. |
| `--product-id` | long, required | ID of the location product billed on the contract's invoices; its current price is used when this line has no price override. |
| `--notes` | string | Optional operator notes about this recurring product line. |
| `--quantity` | int, required | Number of product units billed in each contract billing cycle; must be at least 1. |
| `--price` | decimal | Optional per-unit price override in the location's currency; when null, the linked product's price is used. |
| `--repeat-from` | DateTime | Optional UTC date and time for the first invoice period that includes this product line; inclusive, and null starts billing immediately. |
| `--repeat-until` | DateTime | Optional UTC date and time for the first invoice period that excludes this product line; exclusive, and null continues billing indefinitely. |
| `--apply-pro-rating` | bool | Whether this line requests prorating when it ends during an invoice period; the product's setting can also enable prorating, and the contract plan must have ProrateDaysBefore configured. |

#### ContractProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the customer's contract; it determines the location and billing cycle that will receive this recurring product line. |
| `--product-id` | long | ID of the location product billed on the contract's invoices; its current price is used when this line has no price override. |
| `--notes` | string | Optional operator notes about this recurring product line. |
| `--quantity` | int | Number of product units billed in each contract billing cycle; must be at least 1. |
| `--price` | decimal | Optional per-unit price override in the location's currency; when null, the linked product's price is used. |
| `--repeat-from` | DateTime | Optional UTC date and time for the first invoice period that includes this product line; inclusive, and null starts billing immediately. |
| `--repeat-until` | DateTime | Optional UTC date and time for the first invoice period that excludes this product line; exclusive, and null continues billing indefinitely. |
| `--apply-pro-rating` | bool | Whether this line requests prorating when it ends during an invoice period; the product's setting can also enable prorating, and the contract plan must have ProrateDaysBefore configured. |

#### ContractProduct PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-contract-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-contract-coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus contractproducts update <id> --coworker-contract-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### ContractProduct (key fields)

`Id`, `CoworkerContractCoworkerFullName`, `ProductName`, `Quantity`, `Price`

<!-- END:GENERATED entity=ContractProducts -->
