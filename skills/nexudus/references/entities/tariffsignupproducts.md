# TariffSignupProducts

<!-- BEGIN:GENERATED entity=TariffSignupProducts -->

TariffSignupProducts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffsignupproducts list --agent` | List all tariffsignupproducts |
| `nexudus tariffsignupproducts list --id <id> --agent` | Filter by single ID |
| `nexudus tariffsignupproducts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffsignupproducts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffsignupproducts list --price <value> --agent` | Filter tariffsignupproducts by properties |
| `nexudus tariffsignupproducts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffsignupproducts get <id> --agent` | Get single tariffsignupproduct |
| `nexudus tariffsignupproducts create --tariff-id <value> --product-id <value> --agent` | Create tariffsignupproduct |
| `nexudus tariffsignupproducts update <id> --name "New Name" --agent` | Update tariffsignupproduct |
| `nexudus tariffsignupproducts delete <id> --yes --agent` | Delete tariffsignupproduct (no prompt) |

#### TariffSignupProduct list filter options

`--tariff-id`, `--product-id`, `--price`, `--refundable`

#### TariffSignupProduct create options

`--tariff-id` (required), `--product-id` (required), `--price`, `--refundable`

#### TariffSignupProduct update options

`--tariff-id`, `--product-id`, `--price`, `--refundable`

### TariffSignupProduct (key fields)

`Id`, `TariffName`, `ProductName`, `Price`

<!-- END:GENERATED entity=TariffSignupProducts -->
