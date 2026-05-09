# TariffProducts

<!-- BEGIN:GENERATED entity=TariffProducts -->

TariffProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffproducts list --agent` | List all tariffproducts |
| `nexudus tariffproducts list --id <id> --agent` | Filter by single ID |
| `nexudus tariffproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffproducts list --tariff-id <value> --product-id <value> --agent` | Filter tariffproducts by properties |
| `nexudus tariffproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffproducts get <id> --agent` | Get single tariffproduct |
| `nexudus tariffproducts create --tariff-id <value> --product-id <value> --agent` | Create tariffproduct |
| `nexudus tariffproducts update <id> --name "New Name" --agent` | Update tariffproduct |
| `nexudus tariffproducts delete <id> --yes --agent` | Delete tariffproduct (no prompt) |

#### TariffProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long |  |
| `--product-id` | long |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long, required |  |
| `--product-id` | long, required |  |

#### TariffProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long |  |
| `--product-id` | long |  |

### TariffProduct (key fields)

`Id`, `TariffName`, `ProductName`

<!-- END:GENERATED entity=TariffProducts -->
