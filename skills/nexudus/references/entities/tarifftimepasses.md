# TariffTimePasses

<!-- BEGIN:GENERATED entity=TariffTimePasses -->

A TariffTimePass links a time pass to a pricing plan (tariff), defining an included allowance of time passes for customers on that plan. The renewal time controls how often the allowance resets.

TariffTimePasses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tarifftimepasses list --agent` | List all tarifftimepasses |
| `nexudus tarifftimepasses list --id <id> --agent` | Filter by single ID |
| `nexudus tarifftimepasses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tarifftimepasses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tarifftimepasses list --passes-included <value> --agent` | Filter tarifftimepasses by properties |
| `nexudus tarifftimepasses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tarifftimepasses list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tarifftimepasses get <id> --agent` | Get single tarifftimepass |
| `nexudus tarifftimepasses create --tariff-id <value> --time-pass-id <value> --passes-included <value> --pass-renewal-time <value> --agent` | Create tarifftimepass |
| `nexudus tarifftimepasses update <id> --name "New Name" --agent` | Update tarifftimepass |
| `nexudus tarifftimepasses delete <id> --yes --agent` | Delete tarifftimepass (no prompt) |

#### TariffTimePass list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the plan linked to this record |
| `--time-pass-id` | long | ID of the pass linked to this record |
| `--passes-included` | int | Number of passes included |
| `--from-passes-included` | range | |
| `--to-passes-included` | range | |
| `--pass-renewal-time` | enum | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffTimePass sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TariffTimePass create options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long, required | ID of the plan linked to this record |
| `--time-pass-id` | long, required | ID of the pass linked to this record |
| `--passes-included` | int, required | Number of passes included |
| `--pass-renewal-time` | enum, required | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |

#### TariffTimePass update options

| Option | Type | Description |
| --- | --- | --- |
| `--tariff-id` | long | ID of the plan linked to this record |
| `--time-pass-id` | long | ID of the pass linked to this record |
| `--passes-included` | int | Number of passes included |
| `--pass-renewal-time` | enum | How often will this credit amount will expire and be issued again. Most common option is TariffMonth, which follows the plan renewal cycle. |

### TariffTimePass (key fields)

`Id`, `TariffName`, `TimePassName`, `PassesIncluded`

#### TariffTimePass enum values

| Option | Valid values |
| ------ | ------------ |
| `--pass-renewal-time` | `1` Week, `2` CalendarMonth, `3` TariffMonth, `4` Year, `5` Day |

<!-- END:GENERATED entity=TariffTimePasses -->
