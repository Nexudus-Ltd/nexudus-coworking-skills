# HelpDeskDepartments

<!-- BEGIN:GENERATED entity=HelpDeskDepartments -->

HelpDeskDepartments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus helpdeskdepartments list --agent` | List all helpdeskdepartments |
| `nexudus helpdeskdepartments list --id <id> --agent` | Filter by single ID |
| `nexudus helpdeskdepartments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus helpdeskdepartments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus helpdeskdepartments list --business-id <value> --name <value> --agent` | Filter helpdeskdepartments by properties |
| `nexudus helpdeskdepartments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus helpdeskdepartments get <id> --agent` | Get single helpdeskdepartment |
| `nexudus helpdeskdepartments create --business-id <value> --name <value> --description <value> --agent` | Create helpdeskdepartment |
| `nexudus helpdeskdepartments update <id> --name "New Name" --agent` | Update helpdeskdepartment |
| `nexudus helpdeskdepartments delete <id> --yes --agent` | Delete helpdeskdepartment (no prompt) |

#### HelpDeskDepartment list filter options

`--business-id`, `--name`, `--description`, `--active`, `--task-list-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### HelpDeskDepartment create options

`--business-id` (required), `--name` (required), `--description` (required), `--active`, `--managers` (list, repeat flag), `--added-managers` (list, repeat flag), `--removed-managers` (list, repeat flag), `--task-list-id`

#### HelpDeskDepartment update options

`--business-id`, `--name`, `--description`, `--active`, `--managers` (list, repeat flag), `--added-managers` (list, repeat flag), `--removed-managers` (list, repeat flag), `--task-list-id`

**List properties (only returned by `get`, not by `list`):** `Managers`, `AddedManagers`, `RemovedManagers`

<!-- END:GENERATED entity=HelpDeskDepartments -->
