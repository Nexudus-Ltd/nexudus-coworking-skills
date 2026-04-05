# TariffTimePasses

<!-- BEGIN:GENERATED entity=TariffTimePasses -->

TariffTimePasses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tarifftimepasses list --agent` | List all tarifftimepasses |
| `nexudus tarifftimepasses list --id <id> --agent` | Filter by single ID |
| `nexudus tarifftimepasses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tarifftimepasses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tarifftimepasses list --passes-included <value> --agent` | Filter tarifftimepasses by properties |
| `nexudus tarifftimepasses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tarifftimepasses get <id> --agent` | Get single tarifftimepass |
| `nexudus tarifftimepasses create --tariff-id <value> --time-pass-id <value> --passes-included <value> --agent` | Create tarifftimepass |
| `nexudus tarifftimepasses update <id> --name "New Name" --agent` | Update tarifftimepass |
| `nexudus tarifftimepasses delete <id> --yes --agent` | Delete tarifftimepass (no prompt) |

#### TariffTimePass list filter options

`--tariff-id`, `--time-pass-id`, `--passes-included`, `--from-passes-included` (range), `--to-passes-included` (range), `--pass-renewal-time`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TariffTimePass create options

`--tariff-id` (required), `--time-pass-id` (required), `--passes-included` (required), `--pass-renewal-time`

#### TariffTimePass update options

`--tariff-id`, `--time-pass-id`, `--passes-included`, `--pass-renewal-time`

### TariffTimePass (key fields)

`Id`, `TariffName`, `TimePassName`, `PassesIncluded`

<!-- END:GENERATED entity=TariffTimePasses -->
