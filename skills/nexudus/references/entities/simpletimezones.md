# SimpleTimeZones

<!-- BEGIN:GENERATED entity=SimpleTimeZones -->

SimpleTimeZones support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus simpletimezones list --agent` | List all simpletimezones |
| `nexudus simpletimezones list --id <id> --agent` | Filter by single ID |
| `nexudus simpletimezones list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus simpletimezones list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus simpletimezones list --name <value> --description <value> --agent` | Filter simpletimezones by properties |
| `nexudus simpletimezones list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus simpletimezones get <id> --agent` | Get single simpletimezone |
| `nexudus simpletimezones update <id> --name "New Name" --agent` | Update simpletimezone |

#### SimpleTimeZone list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--description` | string |  |
| `--time-offset` | string |  |
| `--uses-summer-time` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SimpleTimeZone update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--description` | string |  |
| `--time-offset` | string |  |
| `--uses-summer-time` | bool |  |

<!-- END:GENERATED entity=SimpleTimeZones -->
