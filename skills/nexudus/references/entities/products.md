# Products

<!-- BEGIN:GENERATED entity=Products -->

A **Product** represents an item that can be sold to customers. Products can be sold via contracts (`ContractProduct` entity), added to bookings (`BookingProduct` entity), or purchased directly (`CoworkerProduct` entity).

Products support both one-off sales and recurring charges. Recurring charges can be set to daily, weekly, monthly, or yearly frequencies, or charged every time a contract is invoiced. For invoice-linked recurring charges, prefer using `ContractProduct` to associate the sale directly with a specific contract rather than relying on the customer's `MainContract`.

Use `AvailableAs` to control whether a product can be sold as a one-off purchase, a recurring charge, or both. The `SystemProductType` field categorises the product (e.g. day pass, credit bundle, booking product, stationery, or other).

Products can optionally track stock levels, be restricted to specific pricing plans (tariffs), and be limited to members or contacts only.

Products support Search, Get, Create, Update, Delete.
Products also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus products list --agent` | List all products |
| `nexudus products list --id <id> --agent` | Filter by single ID |
| `nexudus products list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus products list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus products list --name <value> --description <value> --agent` | Filter products by properties |
| `nexudus products list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus products get <id> --agent` | Get single product |
| `nexudus products create --business-id <value> --name <value> --system-product-type <value> --description <value> --display-order <value> --price <value> --currency-id <value> --available-as <value> --agent` | Create product |
| `nexudus products update <id> --name "New Name" --agent` | Update product |
| `nexudus products delete <id> --yes --agent` | Delete product (no prompt) |
| `nexudus products commands --agent` | List available entity commands |
| `nexudus products run-command <key> <ids> --agent` | Run entity command |

#### Product list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Product name |
| `--system-product-type` | enum | Category of the product: DayPass, CreditBundle, Stationery, BookingFeature, BookingProducts, or Other |
| `--description` | string | Product description |
| `--invoice-display` | string | Custom text shown on the invoice line instead of the product name |
| `--sku` | string | SKU code |
| `--tags` | string | Tags |
| `--display-order` | int | Display order |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--price` | decimal | Product price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--visible` | bool | Whether the product is visible to customers on the members portal and mobile app |
| `--sync-square` | bool | Sync to Square |
| `--currency-id` | long |  |
| `--tax-rate-id` | long |  |
| `--reduced-tax-rate-id` | long |  |
| `--exempt-tax-rate-id` | long |  |
| `--financial-account-id` | long |  |
| `--available-as` | enum | Controls whether the product can be sold as a one-off purchase, a recurring charge, or both (RecurrentOrOneOff, OnlyRecurrent, OnlyOneOff) |
| `--only-for-contacts` | bool | Restrict purchase to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict purchase to customers with an active contract (members) |
| `--archived` | bool | Whether the product is archived. Archived products cannot be sold but existing charges remain active |
| `--starred` | bool | Mark the product as featured or highlighted |
| `--track-stock` | bool | Enable stock tracking for this product. When enabled, each sale reduces the stock count |
| `--allow-negative-stock` | bool | Allow sales to continue even when stock reaches zero |
| `--stock-alert-level` | int | Stock level at which a low-stock alert is triggered |
| `--from-stock-alert-level` | range | |
| `--to-stock-alert-level` | range | |
| `--apply-pro-rating` | bool | Whether to pro-rate the price when the product is added or removed part-way through a billing period |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--invoice-coworker` | bool | Whether to invoice the customer directly rather than their company or team |
| `--sync-nex-kiosk` | bool | Sync to NexKiosk |
| `--create-delivery` | bool | Automatically create a delivery record for the customer when this product is purchased |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Product create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required | Product name |
| `--system-product-type` | enum, required | Category of the product: DayPass, CreditBundle, Stationery, BookingFeature, BookingProducts, or Other |
| `--description` | string, required | Product description |
| `--invoice-display` | string | Custom text shown on the invoice line instead of the product name |
| `--sku` | string | SKU code |
| `--tags` | string | Tags |
| `--display-order` | int, required | Display order |
| `--price` | decimal, required | Product price |
| `--visible` | bool | Whether the product is visible to customers on the members portal and mobile app |
| `--sync-square` | bool | Sync to Square |
| `--currency-id` | long, required |  |
| `--tax-rate-id` | long |  |
| `--reduced-tax-rate-id` | long |  |
| `--exempt-tax-rate-id` | long |  |
| `--financial-account-id` | long |  |
| `--available-as` | enum, required | Controls whether the product can be sold as a one-off purchase, a recurring charge, or both (RecurrentOrOneOff, OnlyRecurrent, OnlyOneOff) |
| `--only-for-contacts` | bool | Restrict purchase to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict purchase to customers with an active contract (members) |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--archived` | bool | Whether the product is archived. Archived products cannot be sold but existing charges remain active |
| `--starred` | bool | Mark the product as featured or highlighted |
| `--track-stock` | bool | Enable stock tracking for this product. When enabled, each sale reduces the stock count |
| `--allow-negative-stock` | bool | Allow sales to continue even when stock reaches zero |
| `--stock-alert-level` | int | Stock level at which a low-stock alert is triggered |
| `--apply-pro-rating` | bool | Whether to pro-rate the price when the product is added or removed part-way through a billing period |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--invoice-coworker` | bool | Whether to invoice the customer directly rather than their company or team |
| `--sync-nex-kiosk` | bool | Sync to NexKiosk |
| `--create-delivery` | bool | Automatically create a delivery record for the customer when this product is purchased |

#### Product update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Product name |
| `--system-product-type` | enum | Category of the product: DayPass, CreditBundle, Stationery, BookingFeature, BookingProducts, or Other |
| `--description` | string | Product description |
| `--invoice-display` | string | Custom text shown on the invoice line instead of the product name |
| `--sku` | string | SKU code |
| `--tags` | string | Tags |
| `--display-order` | int | Display order |
| `--price` | decimal | Product price |
| `--visible` | bool | Whether the product is visible to customers on the members portal and mobile app |
| `--sync-square` | bool | Sync to Square |
| `--currency-id` | long |  |
| `--tax-rate-id` | long |  |
| `--reduced-tax-rate-id` | long |  |
| `--exempt-tax-rate-id` | long |  |
| `--financial-account-id` | long |  |
| `--available-as` | enum | Controls whether the product can be sold as a one-off purchase, a recurring charge, or both (RecurrentOrOneOff, OnlyRecurrent, OnlyOneOff) |
| `--only-for-contacts` | bool | Restrict purchase to contacts (customers without an active contract) |
| `--only-for-members` | bool | Restrict purchase to customers with an active contract (members) |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--archived` | bool | Whether the product is archived. Archived products cannot be sold but existing charges remain active |
| `--starred` | bool | Mark the product as featured or highlighted |
| `--track-stock` | bool | Enable stock tracking for this product. When enabled, each sale reduces the stock count |
| `--allow-negative-stock` | bool | Allow sales to continue even when stock reaches zero |
| `--stock-alert-level` | int | Stock level at which a low-stock alert is triggered |
| `--apply-pro-rating` | bool | Whether to pro-rate the price when the product is added or removed part-way through a billing period |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--invoice-coworker` | bool | Whether to invoice the customer directly rather than their company or team |
| `--sync-nex-kiosk` | bool | Sync to NexKiosk |
| `--create-delivery` | bool | Automatically create a delivery record for the customer when this product is purchased |

### Product (key fields)

`Id`, `BusinessName`, `Name`, `Description`, `Sku`, `Tags`, `DisplayOrder`, `Price`, `Visible`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`, `TrackStock`, `CurrentStock`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

#### Product enum values

| Option | Valid values |
| ------ | ------------ |
| `--system-product-type` | `0` None, `1` DayPass, `2` CreditBundle, `3` Stationery, `4` BookingFeature, `5` BookingProducts, `99` Other |
| `--available-as` | `0` None, `1` RecurrentOrOneOff, `2` OnlyRecurrent, `3` OnlyOneOff |

<!-- END:GENERATED entity=Products -->
