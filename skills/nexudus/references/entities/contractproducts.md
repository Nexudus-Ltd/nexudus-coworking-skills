# ContractProducts

<!-- BEGIN:GENERATED entity=ContractProducts -->

ContractProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractproducts list --agent` | List all contractproducts |
| `nexudus contractproducts list --id <id> --agent` | Filter by single ID |
| `nexudus contractproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractproducts list --quantity <value> --price <value> --agent` | Filter contractproducts by properties |
| `nexudus contractproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractproducts get <id> --agent` | Get single contractproduct |
| `nexudus contractproducts create --coworker-contract-id <value> --product-id <value> --quantity <value> --agent` | Create contractproduct |
| `nexudus contractproducts update <id> --name "New Name" --agent` | Update contractproduct |
| `nexudus contractproducts delete <id> --yes --agent` | Delete contractproduct (no prompt) |

#### ContractProduct list filter options

`--coworker-contract-id`, `--product-id`, `--notes`, `--quantity`, `--from-quantity` (range), `--to-quantity` (range), `--price`, `--from-price` (range), `--to-price` (range), `--repeat-from`, `--from-repeat-from` (range), `--to-repeat-from` (range), `--repeat-until`, `--from-repeat-until` (range), `--to-repeat-until` (range), `--apply-pro-rating`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ContractProduct create options

`--coworker-contract-id` (required), `--product-id` (required), `--notes`, `--quantity` (required), `--price`, `--repeat-from`, `--repeat-until`, `--apply-pro-rating`

#### ContractProduct update options

`--coworker-contract-id`, `--product-id`, `--notes`, `--quantity`, `--price`, `--repeat-from`, `--repeat-until`, `--apply-pro-rating`

### ContractProduct (key fields)

`Id`, `CoworkerContractCoworkerFullName`, `ProductName`, `Quantity`, `Price`

<!-- END:GENERATED entity=ContractProducts -->
