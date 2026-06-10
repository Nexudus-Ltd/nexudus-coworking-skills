# UserRoles

<!-- BEGIN:GENERATED entity=UserRoles -->

A **UserRole** links a user to a role, granting that user the permissions defined by the role for a specific business location.

UserRoles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus userroles list --agent` | List all userroles |
| `nexudus userroles list --id <id> --agent` | Filter by single ID |
| `nexudus userroles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus userroles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus userroles list --business-id <value> --name <value> --agent` | Filter userroles by properties |
| `nexudus userroles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus userroles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus userroles get <id> --agent` | Get single userrole |
| `nexudus userroles create --business-id <value> --name <value> --agent` | Create userrole |
| `nexudus userroles update <id> --name "New Name" --agent` | Update userrole |
| `nexudus userroles delete <id> --yes --agent` | Delete userrole (no prompt) |

#### UserRole list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this user role |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### UserRole sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### UserRole create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this user role |
| `--roles` | list, repeat flag | List of roles linked to this record |
| `--added-roles` | list, repeat flag | The added roles value for this user role |
| `--removed-roles` | list, repeat flag | The removed roles value for this user role |
| `--users` | list, repeat flag | List of users linked to this record |
| `--added-users` | list, repeat flag | The added users value for this user role |
| `--removed-users` | list, repeat flag | The removed users value for this user role |

#### UserRole update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this user role |
| `--roles` | list, repeat flag | List of roles linked to this record |
| `--added-roles` | list, repeat flag | The added roles value for this user role |
| `--removed-roles` | list, repeat flag | The removed roles value for this user role |
| `--users` | list, repeat flag | List of users linked to this record |
| `--added-users` | list, repeat flag | The added users value for this user role |
| `--removed-users` | list, repeat flag | The removed users value for this user role |

**List properties (only returned by `get`, not by `list`):** `Roles`, `AddedRoles`, `RemovedRoles`, `Users`, `AddedUsers`, `RemovedUsers`

<!-- END:GENERATED entity=UserRoles -->
