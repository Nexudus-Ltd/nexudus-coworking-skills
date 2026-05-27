# ResourceProducts

<!-- BEGIN:GENERATED entity=ResourceProducts -->

A **ResourceProduct** links a product to a resource, enabling products to be offered as add-ons when booking that resource (e.g. catering, AV equipment, room setup).

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

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--invoice-in-minutes` | bool | Whether to invoice in minutes |
| `--request-quantity` | bool | Whether to request quantity |
| `--visible` | bool | Whether the resource product is visible |
| `--price` | decimal | Price override |
| `--from-price` | range | |
| `--to-price` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResourceProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the resource linked to this record |
| `--product-id` | long, required | ID of the product linked to this record |
| `--invoice-in-minutes` | bool | Whether to invoice in minutes |
| `--request-quantity` | bool | Whether to request quantity |
| `--visible` | bool | Whether the resource product is visible |
| `--price` | decimal | Price override |

#### ResourceProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--invoice-in-minutes` | bool | Whether to invoice in minutes |
| `--request-quantity` | bool | Whether to request quantity |
| `--visible` | bool | Whether the resource product is visible |
| `--price` | decimal | Price override |

### ResourceProduct (key fields)

`Id`, `ResourceName`, `ProductName`, `Visible`

<!-- END:GENERATED entity=ResourceProducts -->
