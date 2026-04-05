# TariffExtraServices

<!-- BEGIN:GENERATED entity=TariffExtraServices -->

TariffExtraServices support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffextraservices list --agent` | List all tariffextraservices |
| `nexudus tariffextraservices list --id <id> --agent` | Filter by single ID |
| `nexudus tariffextraservices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffextraservices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffextraservices list --uses-included <value> --agent` | Filter tariffextraservices by properties |
| `nexudus tariffextraservices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffextraservices get <id> --agent` | Get single tariffextraservice |
| `nexudus tariffextraservices create --tariff-id <value> --extra-service-id <value> --uses-included <value> --agent` | Create tariffextraservice |
| `nexudus tariffextraservices update <id> --name "New Name" --agent` | Update tariffextraservice |
| `nexudus tariffextraservices delete <id> --yes --agent` | Delete tariffextraservice (no prompt) |

#### TariffExtraService list filter options

`--tariff-id`, `--extra-service-id`, `--uses-included`, `--from-uses-included` (range), `--to-uses-included` (range), `--service-renewal-time`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TariffExtraService create options

`--tariff-id` (required), `--extra-service-id` (required), `--uses-included` (required), `--service-renewal-time`

#### TariffExtraService update options

`--tariff-id`, `--extra-service-id`, `--uses-included`, `--service-renewal-time`

### TariffExtraService (key fields)

`Id`, `TariffName`, `ExtraServiceName`, `UsesIncluded`

<!-- END:GENERATED entity=TariffExtraServices -->
