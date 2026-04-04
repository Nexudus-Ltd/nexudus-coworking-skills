# CrmBoards

<!-- BEGIN:GENERATED entity=CrmBoards -->

CrmBoards support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus crmboards list --agent` | List all crmboards |
| `nexudus crmboards list --id <id> --agent` | Filter by single ID |
| `nexudus crmboards list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus crmboards list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus crmboards list --business-id <value> --name <value> --agent` | Filter crmboards by properties |
| `nexudus crmboards list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus crmboards get <id> --agent` | Get single crmboard |
| `nexudus crmboards create --business-id <value> --name <value> --agent` | Create crmboard |
| `nexudus crmboards update <id> --name "New Name" --agent` | Update crmboard |
| `nexudus crmboards delete <id> --yes --agent` | Delete crmboard (no prompt) |

#### CrmBoard list filter options

`--business-id`, `--name`, `--archived`

#### CrmBoard create options

`--business-id` (required), `--name` (required), `--board-columns` (list, repeat flag), `--added-board-columns` (list, repeat flag), `--removed-board-columns` (list, repeat flag), `--archived`

#### CrmBoard update options

`--business-id`, `--name`, `--board-columns` (list, repeat flag), `--added-board-columns` (list, repeat flag), `--removed-board-columns` (list, repeat flag), `--archived`

**List properties (only returned by `get`, not by `list`):** `BoardColumns`, `AddedBoardColumns`, `RemovedBoardColumns`

<!-- END:GENERATED entity=CrmBoards -->
