# TariffDefaultDueDates

<!-- BEGIN:GENERATED entity=TariffDefaultDueDates -->

TariffDefaultDueDates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffdefaultduedates list --agent` | List all tariffdefaultduedates |
| `nexudus tariffdefaultduedates list --id <id> --agent` | Filter by single ID |
| `nexudus tariffdefaultduedates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffdefaultduedates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffdefaultduedates list --auto-collect-on <value> --auto-collect-after <value> --agent` | Filter tariffdefaultduedates by properties |
| `nexudus tariffdefaultduedates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffdefaultduedates get <id> --agent` | Get single tariffdefaultduedate |
| `nexudus tariffdefaultduedates create --business-id <value> --agent` | Create tariffdefaultduedate |
| `nexudus tariffdefaultduedates update <id> --name "New Name" --agent` | Update tariffdefaultduedate |
| `nexudus tariffdefaultduedates delete <id> --yes --agent` | Delete tariffdefaultduedate (no prompt) |

#### TariffDefaultDueDate list filter options

`--business-id`, `--auto-collect-on`, `--from-auto-collect-on` (range), `--to-auto-collect-on` (range), `--auto-collect-after`, `--from-auto-collect-after` (range), `--to-auto-collect-after` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TariffDefaultDueDate create options

`--business-id` (required), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--auto-collect-on`, `--auto-collect-after`

#### TariffDefaultDueDate update options

`--business-id`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--auto-collect-on`, `--auto-collect-after`

### TariffDefaultDueDate (key fields)

`Id`, `AutoCollectOn`, `AutoCollectAfter`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TariffDefaultDueDates -->
