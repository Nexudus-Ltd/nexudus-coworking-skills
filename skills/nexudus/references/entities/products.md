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
| `nexudus products create --business-id <value> --name <value> --description <value> --display-order <value> --price <value> --currency-id <value> --agent` | Create product |
| `nexudus products update <id> --name "New Name" --agent` | Update product |
| `nexudus products delete <id> --yes --agent` | Delete product (no prompt) |
| `nexudus products commands --agent` | List available entity commands |
| `nexudus products run-command <key> <ids> --agent` | Run entity command |

#### Product list filter options

`--business-id`, `--name`, `--system-product-type`, `--description`, `--invoice-display`, `--sku`, `--tags`, `--display-order`, `--from-display-order` (range), `--to-display-order` (range), `--price`, `--from-price` (range), `--to-price` (range), `--visible`, `--sync-square`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--available-as`, `--only-for-contacts`, `--only-for-members`, `--archived`, `--starred`, `--track-stock`, `--allow-negative-stock`, `--stock-alert-level`, `--from-stock-alert-level` (range), `--to-stock-alert-level` (range), `--apply-pro-rating`, `--new-image-url`, `--clear-image-file`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Product create options

`--business-id` (required), `--name` (required), `--system-product-type`, `--description` (required), `--invoice-display`, `--sku`, `--tags`, `--display-order` (required), `--price` (required), `--visible`, `--sync-square`, `--currency-id` (required), `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--available-as`, `--only-for-contacts`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--archived`, `--starred`, `--track-stock`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--new-image-url`, `--clear-image-file`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`

#### Product update options

`--business-id`, `--name`, `--system-product-type`, `--description`, `--invoice-display`, `--sku`, `--tags`, `--display-order`, `--price`, `--visible`, `--sync-square`, `--currency-id`, `--tax-rate-id`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--financial-account-id`, `--available-as`, `--only-for-contacts`, `--only-for-members`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--archived`, `--starred`, `--track-stock`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--new-image-url`, `--clear-image-file`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`

### Product (key fields)

`Id`, `BusinessName`, `Name`, `Description`, `Sku`, `Tags`, `DisplayOrder`, `Price`, `Visible`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`, `TrackStock`, `CurrentStock`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

#### Product enum values

| Option | Valid values |
| ------ | ------------ |
| `--system-product-type` | `0` None, `1` DayPass, `2` CreditBundle, `3` Stationery, `4` BookingFeature, `5` BookingProducts, `99` Other |
| `--available-as` | `0` None, `1` RecurrentOrOneOff, `2` OnlyRecurrent, `3` OnlyOneOff |

<!-- END:GENERATED entity=Products -->
