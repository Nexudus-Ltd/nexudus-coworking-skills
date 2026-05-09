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

| Option | Type | Description |
| --- | --- | --- |
| `--time-pass-id` | long |  |
| `--tariff-id` | long |  |
| `--price` | decimal | Price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TimePassPrice create options

| Option | Type | Description |
| --- | --- | --- |
| `--time-pass-id` | long, required |  |
| `--tariff-id` | long, required |  |
| `--price` | decimal, required | Price |

#### TimePassPrice update options

| Option | Type | Description |
| --- | --- | --- |
| `--time-pass-id` | long |  |
| `--tariff-id` | long |  |
| `--price` | decimal | Price |

### TimePassPrice (key fields)

`Id`, `TimePassName`, `TariffName`, `Price`

<!-- END:GENERATED entity=TimePassPrices -->
