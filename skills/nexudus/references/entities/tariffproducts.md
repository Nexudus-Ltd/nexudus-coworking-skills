# TariffProducts

<!-- BEGIN:GENERATED entity=TariffProducts -->

A **TariffProduct** links a product to a pricing plan (tariff), making the product automatically included or available as part of that plan's offering.

TariffProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffproducts list --agent` | List all tariffproducts |
| `nexudus tariffproducts list --id <id> --agent` | Filter by single ID |
| `nexudus tariffproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffproducts list --tariff-id <value> --product-id <value> --agent` | Filter tariffproducts by properties |
| `nexudus tariffproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffproducts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tariffproducts get <id> --agent` | Get single tariffproduct |
| `nexudus tariffproducts create --tariff-id <value> --product-id <value> --agent` | Create tariffproduct |
| `nexudus tariffproducts update <id> --name "New Name" --agent` | Update tariffproduct |
| `nexudus tariffproducts delete <id> --yes --agent` | Delete tariffproduct (no prompt) |

#### TariffProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffProduct sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TariffProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long, required | ID of the tariff linked to this record |
| `--product-id` | long, required | ID of the product linked to this record |

#### TariffProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--product-id` | long | ID of the product linked to this record |

### TariffProduct (key fields)

`Id`, `TariffName`, `ProductName`

<!-- END:GENERATED entity=TariffProducts -->
