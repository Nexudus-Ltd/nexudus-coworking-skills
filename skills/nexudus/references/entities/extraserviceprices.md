# ExtraServicePrices

<!-- BEGIN:GENERATED entity=ExtraServicePrices -->

An **ExtraServicePrice** provides an overriding price for an `ExtraService` (resource price) for members on a specific `Tariff` (plan).

When a member whose active plan matches `TariffId` books a resource priced by the linked extra service, the `Price` (and optional `MaximumPrice`) from this record are used instead of the default extra service price.

In most cases it is preferred to create additional `ExtraService` records connected to the same `ResourceTypes` and restricted to specific plans via `ExtraService.Tariffs`, rather than using ExtraServicePrice overrides. Use ExtraServicePrice only when you need a simple price override without duplicating the full extra service configuration.

ExtraServicePrices support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus extraserviceprices list --agent` | List all extraserviceprices |
| `nexudus extraserviceprices list --id <id> --agent` | Filter by single ID |
| `nexudus extraserviceprices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus extraserviceprices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus extraserviceprices list --price <value> --agent` | Filter extraserviceprices by properties |
| `nexudus extraserviceprices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus extraserviceprices get <id> --agent` | Get single extraserviceprice |
| `nexudus extraserviceprices create --extra-service-id <value> --tariff-id <value> --price <value> --agent` | Create extraserviceprice |
| `nexudus extraserviceprices update <id> --name "New Name" --agent` | Update extraserviceprice |
| `nexudus extraserviceprices delete <id> --yes --agent` | Delete extraserviceprice (no prompt) |

#### ExtraServicePrice list filter options

`--extra-service-id` (long), `--tariff-id` (long), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--maximum-price` (decimal), `--from-maximum-price` (range), `--to-maximum-price` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ExtraServicePrice create options

`--extra-service-id` (long, required), `--tariff-id` (long, required), `--price` (decimal, required), `--maximum-price` (decimal)

#### ExtraServicePrice update options

`--extra-service-id` (long), `--tariff-id` (long), `--price` (decimal), `--maximum-price` (decimal)

### ExtraServicePrice (key fields)

`Id`, `ExtraServiceName`, `TariffName`, `Price`

<!-- END:GENERATED entity=ExtraServicePrices -->
