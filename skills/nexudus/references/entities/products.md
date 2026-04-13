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

`--business-id` (long), `--name`, `--system-product-type` (enum), `--description`, `--invoice-display`, `--sku`, `--tags`, `--display-order` (int), `--from-display-order` (range), `--to-display-order` (range), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--visible` (bool), `--sync-square` (bool), `--currency-id` (long), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--available-as` (enum), `--only-for-contacts` (bool), `--only-for-members` (bool), `--archived` (bool), `--starred` (bool), `--track-stock` (bool), `--allow-negative-stock` (bool), `--stock-alert-level` (int), `--from-stock-alert-level` (range), `--to-stock-alert-level` (range), `--apply-pro-rating` (bool), `--new-image-url`, `--clear-image-file` (bool), `--invoice-coworker` (bool), `--sync-nex-kiosk` (bool), `--create-delivery` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Product create options

`--business-id` (long, required), `--name` (required), `--system-product-type` (enum, required), `--description` (required), `--invoice-display`, `--sku`, `--tags`, `--display-order` (int, required), `--price` (decimal, required), `--visible` (bool), `--sync-square` (bool), `--currency-id` (long, required), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--available-as` (enum, required), `--only-for-contacts` (bool), `--only-for-members` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--archived` (bool), `--starred` (bool), `--track-stock` (bool), `--allow-negative-stock` (bool), `--stock-alert-level` (int), `--apply-pro-rating` (bool), `--new-image-url`, `--clear-image-file` (bool), `--invoice-coworker` (bool), `--sync-nex-kiosk` (bool), `--create-delivery` (bool)

#### Product update options

`--business-id` (long), `--name`, `--system-product-type` (enum), `--description`, `--invoice-display`, `--sku`, `--tags`, `--display-order` (int), `--price` (decimal), `--visible` (bool), `--sync-square` (bool), `--currency-id` (long), `--tax-rate-id` (long), `--reduced-tax-rate-id` (long), `--exempt-tax-rate-id` (long), `--financial-account-id` (long), `--available-as` (enum), `--only-for-contacts` (bool), `--only-for-members` (bool), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--archived` (bool), `--starred` (bool), `--track-stock` (bool), `--allow-negative-stock` (bool), `--stock-alert-level` (int), `--apply-pro-rating` (bool), `--new-image-url`, `--clear-image-file` (bool), `--invoice-coworker` (bool), `--sync-nex-kiosk` (bool), `--create-delivery` (bool)

### Product (key fields)

`Id`, `BusinessName`, `Name`, `Description`, `Sku`, `Tags`, `DisplayOrder`, `Price`, `Visible`, `CurrencyCode`, `OnlyForContacts`, `OnlyForMembers`, `Archived`, `TrackStock`, `CurrentStock`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

#### Product enum values

| Option | Valid values |
| ------ | ------------ |
| `--system-product-type` | `0` None, `1` DayPass, `2` CreditBundle, `3` Stationery, `4` BookingFeature, `5` BookingProducts, `99` Other |
| `--available-as` | `0` None, `1` RecurrentOrOneOff, `2` OnlyRecurrent, `3` OnlyOneOff |

<!-- END:GENERATED entity=Products -->
