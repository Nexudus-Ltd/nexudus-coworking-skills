# TaskLists

<!-- BEGIN:GENERATED entity=TaskLists -->

A **TaskList** groups related task items into a named collection for organisation and tracking purposes.

TaskLists support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tasklists list --agent` | List all tasklists |
| `nexudus tasklists list --id <id> --agent` | Filter by single ID |
| `nexudus tasklists list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tasklists list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tasklists list --business-id <value> --name <value> --agent` | Filter tasklists by properties |
| `nexudus tasklists list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tasklists list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tasklists get <id> --agent` | Get single tasklist |
| `nexudus tasklists create --business-id <value> --name <value> --agent` | Create tasklist |
| `nexudus tasklists update <id> --name "New Name" --agent` | Update tasklist |
| `nexudus tasklists delete <id> --yes --agent` | Delete tasklist (no prompt) |

#### TaskList list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this task list |
| `--active` | bool | Whether this task list is currently active |
| `--assign-to-new-contacts` | bool | Whether assign to new contacts is enabled |
| `--assign-to-new-members` | bool | Whether assign to new members is enabled |
| `--assign-to-cancellations` | bool | Whether assign to cancellations is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TaskList sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### TaskList create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this task list |
| `--active` | bool | Whether this task list is currently active |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this task list |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this task list |
| `--assign-to-new-contacts` | bool | Whether assign to new contacts is enabled |
| `--assign-to-new-members` | bool | Whether assign to new members is enabled |
| `--assign-to-cancellations` | bool | Whether assign to cancellations is enabled |

#### TaskList update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this task list |
| `--active` | bool | Whether this task list is currently active |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this task list |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this task list |
| `--assign-to-new-contacts` | bool | Whether assign to new contacts is enabled |
| `--assign-to-new-members` | bool | Whether assign to new members is enabled |
| `--assign-to-cancellations` | bool | Whether assign to cancellations is enabled |

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TaskLists -->
