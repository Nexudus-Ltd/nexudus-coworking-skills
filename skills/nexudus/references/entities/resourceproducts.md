# ResourceProducts

<!-- BEGIN:GENERATED entity=ResourceProducts -->

ResourceProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourceproducts list --agent` | List all resourceproducts |
| `nexudus resourceproducts list --id <id> --agent` | Filter by single ID |
| `nexudus resourceproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resourceproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resourceproducts list --visible <value> --agent` | Filter resourceproducts by properties |
| `nexudus resourceproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resourceproducts get <id> --agent` | Get single resourceproduct |
| `nexudus resourceproducts create --resource-id <value> --product-id <value> --agent` | Create resourceproduct |
| `nexudus resourceproducts update <id> --name "New Name" --agent` | Update resourceproduct |
| `nexudus resourceproducts delete <id> --yes --agent` | Delete resourceproduct (no prompt) |

#### ResourceProduct list filter options

`--resource-id` (long), `--product-id` (long), `--invoice-in-minutes` (bool), `--request-quantity` (bool), `--visible` (bool), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ResourceProduct create options

`--resource-id` (long, required), `--product-id` (long, required), `--invoice-in-minutes` (bool), `--request-quantity` (bool), `--visible` (bool), `--price` (decimal)

#### ResourceProduct update options

`--resource-id` (long), `--product-id` (long), `--invoice-in-minutes` (bool), `--request-quantity` (bool), `--visible` (bool), `--price` (decimal)

### ResourceProduct (key fields)

`Id`, `ResourceName`, `ProductName`, `Visible`

<!-- END:GENERATED entity=ResourceProducts -->
