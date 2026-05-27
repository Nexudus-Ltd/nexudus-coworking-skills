# TaskItems

<!-- BEGIN:GENERATED entity=TaskItems -->

A **TaskItem** represents an individual task or to-do item that can be assigned to staff or customers. Tasks can be organised into lists, have due dates, and track completion status.

TaskItems support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus taskitems list --agent` | List all taskitems |
| `nexudus taskitems list --id <id> --agent` | Filter by single ID |
| `nexudus taskitems list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus taskitems list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus taskitems list --task-list-id <value> --responsible-id <value> --agent` | Filter taskitems by properties |
| `nexudus taskitems list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus taskitems get <id> --agent` | Get single taskitem |
| `nexudus taskitems create --task-list-id <value> --responsible-id <value> --name <value> --delay-in-hours <value> --agent` | Create taskitem |
| `nexudus taskitems update <id> --name "New Name" --agent` | Update taskitem |
| `nexudus taskitems delete <id> --yes --agent` | Delete taskitem (no prompt) |

#### TaskItem list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--task-list-id` | long | ID of the task list linked to this record |
| `--responsible-id` | long | ID of the responsible linked to this record |
| `--name` | string | The name value for this task item |
| `--active` | bool | Whether this task item is currently active |
| `--notify-by-email` | bool | Whether notify by email is enabled |
| `--display-to-everyone` | bool | Whether display to everyone is enabled |
| `--delay-in-hours` | int | The delay in hours value for this task item |
| `--from-delay-in-hours` | range | |
| `--to-delay-in-hours` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TaskItem create options

| Option | Type | Description |
| --- | --- | --- |
| `--task-list-id` | long, required | ID of the task list linked to this record |
| `--responsible-id` | long, required | ID of the responsible linked to this record |
| `--name` | string, required | The name value for this task item |
| `--active` | bool | Whether this task item is currently active |
| `--notify-by-email` | bool | Whether notify by email is enabled |
| `--display-to-everyone` | bool | Whether display to everyone is enabled |
| `--delay-in-hours` | int, required | The delay in hours value for this task item |

#### TaskItem update options

| Option | Type | Description |
| --- | --- | --- |
| `--task-list-id` | long | ID of the task list linked to this record |
| `--responsible-id` | long | ID of the responsible linked to this record |
| `--name` | string | The name value for this task item |
| `--active` | bool | Whether this task item is currently active |
| `--notify-by-email` | bool | Whether notify by email is enabled |
| `--display-to-everyone` | bool | Whether display to everyone is enabled |
| `--delay-in-hours` | int | The delay in hours value for this task item |

#### TaskItem PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notify-by-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus taskitems update <id> --responsible-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=TaskItems -->
