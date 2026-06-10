# SimpleTimeZones

<!-- BEGIN:GENERATED entity=SimpleTimeZones -->

A **SimpleTimeZone** represents a time zone available in the system. Time zones are used to configure business opening hours, booking times, and scheduling across different geographic locations.

SimpleTimeZones support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus simpletimezones list --agent` | List all simpletimezones |
| `nexudus simpletimezones list --id <id> --agent` | Filter by single ID |
| `nexudus simpletimezones list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus simpletimezones list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus simpletimezones list --name <value> --description <value> --agent` | Filter simpletimezones by properties |
| `nexudus simpletimezones list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus simpletimezones list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus simpletimezones get <id> --agent` | Get single simpletimezone |
| `nexudus simpletimezones update <id> --name "New Name" --agent` | Update simpletimezone |

#### SimpleTimeZone list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | The name value for this simple time zone |
| `--description` | string | Free-text description of this simple time zone |
| `--time-offset` | string | The time offset value for this simple time zone |
| `--uses-summer-time` | bool | Whether uses summer time is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SimpleTimeZone sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `TimeOffset` descending. If no `--order-by` is specified, the API returns results ordered by `TimeOffset` (descending).

#### SimpleTimeZone update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | The name value for this simple time zone |
| `--description` | string | Free-text description of this simple time zone |
| `--time-offset` | string | The time offset value for this simple time zone |
| `--uses-summer-time` | bool | Whether uses summer time is enabled |

<!-- END:GENERATED entity=SimpleTimeZones -->
