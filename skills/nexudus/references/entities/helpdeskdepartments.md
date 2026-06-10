# HelpDeskDepartments

<!-- BEGIN:GENERATED entity=HelpDeskDepartments -->

A **HelpDeskDepartment** defines a support department that help desk messages can be assigned to, such as 'Billing', 'Facilities', or 'IT Support'. Departments help route and organize incoming support requests.

HelpDeskDepartments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus helpdeskdepartments list --agent` | List all helpdeskdepartments |
| `nexudus helpdeskdepartments list --id <id> --agent` | Filter by single ID |
| `nexudus helpdeskdepartments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus helpdeskdepartments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus helpdeskdepartments list --business-id <value> --name <value> --agent` | Filter helpdeskdepartments by properties |
| `nexudus helpdeskdepartments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus helpdeskdepartments list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus helpdeskdepartments get <id> --agent` | Get single helpdeskdepartment |
| `nexudus helpdeskdepartments create --business-id <value> --name <value> --description <value> --agent` | Create helpdeskdepartment |
| `nexudus helpdeskdepartments update <id> --name "New Name" --agent` | Update helpdeskdepartment |
| `nexudus helpdeskdepartments delete <id> --yes --agent` | Delete helpdeskdepartment (no prompt) |

#### HelpDeskDepartment list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this help desk department |
| `--description` | string | Free-text description of this help desk department |
| `--active` | bool | Whether this help desk department is currently active |
| `--task-list-id` | long | ID of the task list linked to this record |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### HelpDeskDepartment sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### HelpDeskDepartment create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this help desk department |
| `--description` | string, required | Free-text description of this help desk department |
| `--active` | bool | Whether this help desk department is currently active |
| `--managers` | list, repeat flag | List of managers linked to this record |
| `--added-managers` | list, repeat flag | The added managers value for this help desk department |
| `--removed-managers` | list, repeat flag | The removed managers value for this help desk department |
| `--task-list-id` | long | ID of the task list linked to this record |

#### HelpDeskDepartment update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this help desk department |
| `--description` | string | Free-text description of this help desk department |
| `--active` | bool | Whether this help desk department is currently active |
| `--managers` | list, repeat flag | List of managers linked to this record |
| `--added-managers` | list, repeat flag | The added managers value for this help desk department |
| `--removed-managers` | list, repeat flag | The removed managers value for this help desk department |
| `--task-list-id` | long | ID of the task list linked to this record |

**List properties (only returned by `get`, not by `list`):** `Managers`, `AddedManagers`, `RemovedManagers`

<!-- END:GENERATED entity=HelpDeskDepartments -->
