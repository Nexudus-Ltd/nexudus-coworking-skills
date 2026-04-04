# TaskLists

<!-- BEGIN:GENERATED entity=TaskLists -->

TaskLists support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tasklists list --agent` | List all tasklists |
| `nexudus tasklists list --id <id> --agent` | Filter by single ID |
| `nexudus tasklists list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tasklists list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tasklists list --business-id <value> --name <value> --agent` | Filter tasklists by properties |
| `nexudus tasklists list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tasklists get <id> --agent` | Get single tasklist |
| `nexudus tasklists create --business-id <value> --name <value> --agent` | Create tasklist |
| `nexudus tasklists update <id> --name "New Name" --agent` | Update tasklist |
| `nexudus tasklists delete <id> --yes --agent` | Delete tasklist (no prompt) |

#### TaskList list filter options

`--business-id`, `--name`, `--active`, `--assign-to-new-contacts`, `--assign-to-new-members`, `--assign-to-cancellations`

#### TaskList create options

`--business-id` (required), `--name` (required), `--active`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--assign-to-new-contacts`, `--assign-to-new-members`, `--assign-to-cancellations`, `--task-items` (list, repeat flag), `--added-task-items` (list, repeat flag), `--removed-task-items` (list, repeat flag)

#### TaskList update options

`--business-id`, `--name`, `--active`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--assign-to-new-contacts`, `--assign-to-new-members`, `--assign-to-cancellations`, `--task-items` (list, repeat flag), `--added-task-items` (list, repeat flag), `--removed-task-items` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `TaskItems`, `AddedTaskItems`, `RemovedTaskItems`

<!-- END:GENERATED entity=TaskLists -->
