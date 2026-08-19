# TariffSignupProducts

<!-- BEGIN:GENERATED entity=TariffSignupProducts -->

A **TariffSignupProduct** links a product to a pricing plan (tariff) as a one-time sign-up charge. Products linked this way are automatically added to a customer's first invoice when they join the plan.

TariffSignupProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffsignupproducts list --agent` | List all tariffsignupproducts |
| `nexudus tariffsignupproducts list --id <id> --agent` | Filter by single ID |
| `nexudus tariffsignupproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffsignupproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffsignupproducts list --tariff-name <value> --product-name <value> --agent` | Filter tariffsignupproducts by properties |
| `nexudus tariffsignupproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffsignupproducts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tariffsignupproducts get <id> --agent` | Get single tariffsignupproduct |
| `nexudus tariffsignupproducts create --tariff-id <value> --product-id <value> --agent` | Create tariffsignupproduct |
| `nexudus tariffsignupproducts update <id> --name "New Name" --agent` | Update tariffsignupproduct |
| `nexudus tariffsignupproducts delete <id> --yes --agent` | Delete tariffsignupproduct (no prompt) |

#### TariffSignupProduct list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--tariff-name` | string | Tariff name |
| `--product-id` | long | ID of the product linked to this record |
| `--product-name` | string | Product name |
| `--product-price` | decimal | Product price |
| `--from-product-price` | range | |
| `--to-product-price` | range | |
| `--product-currency-code` | string | Product currency code |
| `--price` | decimal | Signup product price override |
| `--from-price` | range | |
| `--to-price` | range | |
| `--refundable` | bool | Whether the signup product is refundable |
| `--invoice-during-online-checkout` | bool | Whether invoice during online checkout is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffSignupProduct sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TariffSignupProduct create options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long, required | ID of the tariff linked to this record |
| `--product-id` | long, required | ID of the product linked to this record |
| `--price` | decimal | Signup product price override |
| `--refundable` | bool | Whether the signup product is refundable |
| `--invoice-during-online-checkout` | bool | Whether invoice during online checkout is enabled |

#### TariffSignupProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--product-id` | long | ID of the product linked to this record |
| `--price` | decimal | Signup product price override |
| `--refundable` | bool | Whether the signup product is refundable |
| `--invoice-during-online-checkout` | bool | Whether invoice during online checkout is enabled |

### TariffSignupProduct (key fields)

`Id`, `TariffName`, `ProductName`, `Price`

<!-- END:GENERATED entity=TariffSignupProducts -->
