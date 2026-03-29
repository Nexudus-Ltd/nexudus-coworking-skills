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
| `nexudus products list --query "search" --agent` | Search products by name |
| `nexudus products list --page 2 --size 10 --agent` | Paginated list |
| `nexudus products get <id> --agent` | Get single product |
| `nexudus products create --business <value> --name <value> --price <value> --description <value> --agent` | Create product |
| `nexudus products update <id> --name "New Name" --agent` | Update product |
| `nexudus products delete <id> --yes --agent` | Delete product (no prompt) |
| `nexudus products commands --agent` | List available entity commands |
| `nexudus products run-command <key> <ids> --agent` | Run entity command |

#### Product create options

`--business` (required), `--name` (required), `--price` (required), `--description` (required), `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--track-stock`, `--archived`, `--financial-account-id`, `--system-product-type`, `--invoice-display`, `--sync-square`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--available-as`, `--starred`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`, `--image-url`, `--image-file`, `--clear-image`

#### Product update options

`--name`, `--price`, `--description`, `--sku`, `--tags`, `--visible`, `--currency-id`, `--tax-rate-id`, `--display-order`, `--only-for-members`, `--only-for-contacts`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--track-stock`, `--archived`, `--financial-account-id`, `--system-product-type`, `--invoice-display`, `--sync-square`, `--reduced-tax-rate-id`, `--exempt-tax-rate-id`, `--available-as`, `--starred`, `--allow-negative-stock`, `--stock-alert-level`, `--apply-pro-rating`, `--invoice-coworker`, `--sync-nex-kiosk`, `--create-delivery`, `--image-url`, `--image-file`, `--clear-image`

### Product (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`, `Price`, `Description`, `Sku`, `Tags`, `Visible`, `CurrencyCode`, `DisplayOrder`, `OnlyForMembers`, `OnlyForContacts`, `TrackStock`, `CurrentStock`, `Archived`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

#### Product enum values

| Option | Valid values |
| ------ | ------------ |
| `--system-product-type` | `0` None, `1` DayPass, `2` CreditBundle, `3` Stationery, `4` BookingFeature, `5` BookingProducts, `99` Other |
| `--available-as` | `0` None, `1` RecurrentOrOneOff, `2` OnlyRecurrent, `3` OnlyOneOff |

<!-- END:GENERATED entity=Products -->
