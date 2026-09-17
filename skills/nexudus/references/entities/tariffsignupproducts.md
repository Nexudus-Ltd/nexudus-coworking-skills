# TariffSignupProducts

<!-- BEGIN:GENERATED entity=TariffSignupProducts -->

A sign-up product (internally TariffSignupProduct) attaches a one-off deposit or sign-up fee to a plan (internally tariff). Creating a contract on that plan copies every sign-up product into a contract deposit (ContractDeposit), carrying over its price, refundable flag and online-checkout flag, and flags the contract to include the sign-up fee on its first eligible invoice. Sign-up product prices count towards the plan's total sign-up price but not towards its recurring total price. Changes here affect only contracts created afterwards; contracts that already exist keep the deposits they were created with. Recurring add-ons belong on plan components (TariffProduct) instead.

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
| `--tariff-id` | long | ID of the plan this sign-up fee belongs to; required, and it determines the owning location. Every contract created afterwards on that plan gets a matching deposit. |
| `--tariff-name` | string | Display value for Tariff.Name. |
| `--product-id` | long | ID of the product charged as the sign-up fee or deposit; required, and its own current price is used whenever Price is left null, so reuse an existing product rather than creating a duplicate. |
| `--product-name` | string | Display value for Product.Name. |
| `--product-price` | decimal | Display value for Product.Price. |
| `--from-product-price` | range | |
| `--to-product-price` | range | |
| `--product-currency-code` | string | Display value for Product.Currency.Code. |
| `--price` | decimal | Optional amount charged for this sign-up fee, in the location's currency; when null the linked product's own current price is used instead. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--refundable` | bool | Whether the deposit created from this sign-up fee is refunded when the contract ends, producing an unpaid credit note that can also be used to offset exit or damage fees. |
| `--invoice-during-online-checkout` | bool | Whether this fee is charged during the customer's online checkout instead of waiting for the contract's first eligible invoice. |
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
| `--tariff-id` | long, required | ID of the plan this sign-up fee belongs to; required, and it determines the owning location. Every contract created afterwards on that plan gets a matching deposit. |
| `--product-id` | long, required | ID of the product charged as the sign-up fee or deposit; required, and its own current price is used whenever Price is left null, so reuse an existing product rather than creating a duplicate. |
| `--price` | decimal | Optional amount charged for this sign-up fee, in the location's currency; when null the linked product's own current price is used instead. |
| `--refundable` | bool | Whether the deposit created from this sign-up fee is refunded when the contract ends, producing an unpaid credit note that can also be used to offset exit or damage fees. |
| `--invoice-during-online-checkout` | bool | Whether this fee is charged during the customer's online checkout instead of waiting for the contract's first eligible invoice. |

#### TariffSignupProduct update options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the plan this sign-up fee belongs to; required, and it determines the owning location. Every contract created afterwards on that plan gets a matching deposit. |
| `--product-id` | long | ID of the product charged as the sign-up fee or deposit; required, and its own current price is used whenever Price is left null, so reuse an existing product rather than creating a duplicate. |
| `--price` | decimal | Optional amount charged for this sign-up fee, in the location's currency; when null the linked product's own current price is used instead. |
| `--refundable` | bool | Whether the deposit created from this sign-up fee is refunded when the contract ends, producing an unpaid credit note that can also be used to offset exit or damage fees. |
| `--invoice-during-online-checkout` | bool | Whether this fee is charged during the customer's online checkout instead of waiting for the contract's first eligible invoice. |

### TariffSignupProduct (key fields)

`Id`, `TariffName`, `ProductName`, `Price`

<!-- END:GENERATED entity=TariffSignupProducts -->
