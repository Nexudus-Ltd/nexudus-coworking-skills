# HelpDeskDepartments

<!-- BEGIN:GENERATED entity=HelpDeskDepartments -->

A support department (HelpDeskDepartment) routes customer support tickets to its managers and can add a task list to the customer.

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
| `--business-id` | long | ID of the location that owns this support department; it is supplied from the agent context. |
| `--name` | string | Required localized name used to identify this support department when assigning support tickets. |
| `--description` | string | Required localized text explaining the purpose or scope of this support department. |
| `--active` | bool | Whether customers can select this support department when submitting a support ticket; inactive departments are not offered to customers. |
| `--task-list-id` | long | Optional ID of the task list automatically added to the customer when a ticket is created or updated for this support department. |
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
| `--business-id` | long, required | ID of the location that owns this support department; it is supplied from the agent context. |
| `--name` | string, required | Required localized name used to identify this support department when assigning support tickets. |
| `--description` | string, required | Required localized text explaining the purpose or scope of this support department. |
| `--active` | bool | Whether customers can select this support department when submitting a support ticket; inactive departments are not offered to customers. |
| `--managers` | list, repeat flag | List of user IDs for managers notified about new tickets and comments assigned to this support department. |
| `--added-managers` | list, repeat flag | The added managers value for this help desk department |
| `--removed-managers` | list, repeat flag | The removed managers value for this help desk department |
| `--task-list-id` | long | Optional ID of the task list automatically added to the customer when a ticket is created or updated for this support department. |

#### HelpDeskDepartment update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this support department; it is supplied from the agent context. |
| `--name` | string | Required localized name used to identify this support department when assigning support tickets. |
| `--description` | string | Required localized text explaining the purpose or scope of this support department. |
| `--active` | bool | Whether customers can select this support department when submitting a support ticket; inactive departments are not offered to customers. |
| `--managers` | list, repeat flag | List of user IDs for managers notified about new tickets and comments assigned to this support department. |
| `--added-managers` | list, repeat flag | The added managers value for this help desk department |
| `--removed-managers` | list, repeat flag | The removed managers value for this help desk department |
| `--task-list-id` | long | Optional ID of the task list automatically added to the customer when a ticket is created or updated for this support department. |

**List properties (only returned by `get`, not by `list`):** `Managers`, `AddedManagers`, `RemovedManagers`

<!-- END:GENERATED entity=HelpDeskDepartments -->
