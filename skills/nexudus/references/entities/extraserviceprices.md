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
| `nexudus extraserviceprices list --extra-service-name <value> --tariff-name <value> --agent` | Filter extraserviceprices by properties |
| `nexudus extraserviceprices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus extraserviceprices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus extraserviceprices get <id> --agent` | Get single extraserviceprice |
| `nexudus extraserviceprices create --extra-service-id <value> --tariff-id <value> --price <value> --agent` | Create extraserviceprice |
| `nexudus extraserviceprices update <id> --name "New Name" --agent` | Update extraserviceprice |
| `nexudus extraserviceprices delete <id> --yes --agent` | Delete extraserviceprice (no prompt) |

#### ExtraServicePrice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--extra-service-id` | long | ID of the extra service linked to this record |
| `--extra-service-name` | string | Name of the linked extra service |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--tariff-name` | string | Name of the linked tariff |
| `--price` | decimal | Overriding price charged to members on the specified tariff |
| `--from-price` | range | |
| `--to-price` | range | |
| `--maximum-price` | decimal | Optional maximum price cap for time-based extra services on the specified tariff |
| `--from-maximum-price` | range | |
| `--to-maximum-price` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ExtraServicePrice sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ExtraServicePrice create options

| Option | Type | Description |
| --- | --- | --- |
| `--extra-service-id` | long, required | ID of the extra service linked to this record |
| `--tariff-id` | long, required | ID of the tariff linked to this record |
| `--price` | decimal, required | Overriding price charged to members on the specified tariff |
| `--maximum-price` | decimal | Optional maximum price cap for time-based extra services on the specified tariff |

#### ExtraServicePrice update options

| Option | Type | Description |
| --- | --- | --- |
| `--extra-service-id` | long | ID of the extra service linked to this record |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--price` | decimal | Overriding price charged to members on the specified tariff |
| `--maximum-price` | decimal | Optional maximum price cap for time-based extra services on the specified tariff |

### ExtraServicePrice (key fields)

`Id`, `ExtraServiceName`, `TariffName`, `Price`

<!-- END:GENERATED entity=ExtraServicePrices -->
