# ContractProducts

<!-- BEGIN:GENERATED entity=ContractProducts -->

A **ContractProduct** is a product added to a contract that is billed every time the contract is invoiced. Use `ContractProduct` to append product charges to a specific member's billing cycle alongside the base plan.

**Price** — If `Price` is not set, the price of the underlying product (`ProductPrice`) is used instead. Set `Price` to override the product's default price for this specific contract line.

**Billing window** — `RepeatFrom` and `RepeatUntil` control the date range during which the product is included on invoices. Outside that range the product is silently skipped. Leave both null to bill the product on every invoice.

**Pro-rating** — `ApplyProRating` distributes the charge proportionally across the billing period, but only takes effect when the linked location plan has prorating enabled (`Tariff.ProrateDaysBefore > 0`). If the plan does not have prorating configured, `ApplyProRating` is ignored.

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
| `--coworker-contract-id` | long | Contract to add this product to |
| `--product-id` | long | Product to bill on each contract invoice |
| `--notes` | string | Optional notes or comments about this contract product |
| `--quantity` | int | Number of units |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--price` | decimal | Price override |
| `--from-price` | range | |
| `--to-price` | range | |
| `--repeat-from` | DateTime | Repeat from date |
| `--from-repeat-from` | range | |
| `--to-repeat-from` | range | |
| `--repeat-until` | DateTime | Repeat until date |
| `--from-repeat-until` | range | |
| `--to-repeat-until` | range | |
| `--apply-pro-rating` | bool | Apply pro-rating to this product charge. Only takes effect when the location plan has prorating enabled (Tariff.ProrateDaysBefore > 0). |
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
| `--coworker-contract-id` | long, required | Contract to add this product to |
| `--product-id` | long, required | Product to bill on each contract invoice |
| `--notes` | string | Optional notes or comments about this contract product |
| `--quantity` | int, required | Number of units |
| `--price` | decimal | Price override |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |
| `--apply-pro-rating` | bool | Apply pro-rating to this product charge. Only takes effect when the location plan has prorating enabled (Tariff.ProrateDaysBefore > 0). |

#### ContractProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | Contract to add this product to |
| `--product-id` | long | Product to bill on each contract invoice |
| `--notes` | string | Optional notes or comments about this contract product |
| `--quantity` | int | Number of units |
| `--price` | decimal | Price override |
| `--repeat-from` | DateTime | Repeat from date |
| `--repeat-until` | DateTime | Repeat until date |
| `--apply-pro-rating` | bool | Apply pro-rating to this product charge. Only takes effect when the location plan has prorating enabled (Tariff.ProrateDaysBefore > 0). |

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
