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
| `nexudus tarifftimepasses create --tariff-id <value> --time-pass-id <value> --passes-included <value> --pass-renewal-time <value> --agent` | Create tarifftimepass |
| `nexudus tarifftimepasses update <id> --name "New Name" --agent` | Update tarifftimepass |
| `nexudus tarifftimepasses delete <id> --yes --agent` | Delete tarifftimepass (no prompt) |

#### TariffTimePass list filter options

`--tariff-id` (long), `--time-pass-id` (long), `--passes-included` (int), `--from-passes-included` (range), `--to-passes-included` (range), `--pass-renewal-time` (enum), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TariffTimePass create options

`--tariff-id` (long, required), `--time-pass-id` (long, required), `--passes-included` (int, required), `--pass-renewal-time` (enum, required)

#### TariffTimePass update options

`--tariff-id` (long), `--time-pass-id` (long), `--passes-included` (int), `--pass-renewal-time` (enum)

### TariffTimePass (key fields)

`Id`, `TariffName`, `TimePassName`, `PassesIncluded`

<!-- END:GENERATED entity=TariffTimePasses -->
