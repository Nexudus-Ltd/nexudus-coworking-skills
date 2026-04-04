# TimePassPrices

<!-- BEGIN:GENERATED entity=TimePassPrices -->

TimePassPrices support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus timepassprices list --agent` | List all timepassprices |
| `nexudus timepassprices list --id <id> --agent` | Filter by single ID |
| `nexudus timepassprices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus timepassprices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus timepassprices list --price <value> --agent` | Filter timepassprices by properties |
| `nexudus timepassprices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus timepassprices get <id> --agent` | Get single timepassprice |
| `nexudus timepassprices create --time-pass-id <value> --tariff-id <value> --price <value> --agent` | Create timepassprice |
| `nexudus timepassprices update <id> --name "New Name" --agent` | Update timepassprice |
| `nexudus timepassprices delete <id> --yes --agent` | Delete timepassprice (no prompt) |

#### TimePassPrice list filter options

`--time-pass-id`, `--tariff-id`, `--price`

#### TimePassPrice create options

`--time-pass-id` (required), `--tariff-id` (required), `--price` (required)

#### TimePassPrice update options

`--time-pass-id`, `--tariff-id`, `--price`

### TimePassPrice (key fields)

`Id`, `TimePassName`, `TariffName`, `Price`

<!-- END:GENERATED entity=TimePassPrices -->
