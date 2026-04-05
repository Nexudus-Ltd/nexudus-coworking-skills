# TaskItems

<!-- BEGIN:GENERATED entity=TaskItems -->

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

`--task-list-id`, `--responsible-id`, `--name`, `--active`, `--notify-by-email`, `--display-to-everyone`, `--delay-in-hours`, `--from-delay-in-hours` (range), `--to-delay-in-hours` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### TaskItem create options

`--task-list-id` (required), `--responsible-id` (required), `--name` (required), `--active`, `--notify-by-email`, `--display-to-everyone`, `--delay-in-hours` (required)

#### TaskItem update options

`--task-list-id`, `--responsible-id`, `--name`, `--active`, `--notify-by-email`, `--display-to-everyone`, `--delay-in-hours`

<!-- END:GENERATED entity=TaskItems -->
