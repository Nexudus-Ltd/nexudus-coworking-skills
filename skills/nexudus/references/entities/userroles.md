# UserRoles

<!-- BEGIN:GENERATED entity=UserRoles -->

A User Role is a permission group that assigns one or more global Roles to user accounts across every location they can access; its associated location is organisational only.

UserRoles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus userroles list --agent` | List all userroles |
| `nexudus userroles list --id <id> --agent` | Filter by single ID |
| `nexudus userroles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus userroles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus userroles list --business-id <value> --business-name <value> --agent` | Filter userroles by properties |
| `nexudus userroles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus userroles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus userroles get <id> --agent` | Get single userrole |
| `nexudus userroles create --business-id <value> --name <value> --agent` | Create userrole |
| `nexudus userroles update <id> --name "New Name" --agent` | Update userrole |
| `nexudus userroles delete <id> --yes --agent` | Delete userrole (no prompt) |

#### UserRole list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the organisational location associated with this User Role; keep it at the top-most root location where possible, as it does not limit the permissions granted. |
| `--business-name` | string | Display value for Business.Name. |
| `--name` | string | Required name of this permission group, unique within its organisational location. |
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
| `--business-id` | long, required | ID of the organisational location associated with this User Role; keep it at the top-most root location where possible, as it does not limit the permissions granted. |
| `--name` | string, required | Required name of this permission group, unique within its organisational location. |
| `--roles` | list, repeat flag | List of global Role IDs that define this permission group's permissions; an empty list grants no Role permissions. |
| `--added-roles` | list, repeat flag | IDs added to the Roles relationship. |
| `--removed-roles` | list, repeat flag | IDs removed from the Roles relationship. |
| `--users` | list, repeat flag | List of User IDs assigned to this permission group; an empty list assigns the group to no users, and an update replaces the complete assignment list. |
| `--added-users` | list, repeat flag | IDs added to the Users relationship. |
| `--removed-users` | list, repeat flag | IDs removed from the Users relationship. |

#### UserRole update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the organisational location associated with this User Role; keep it at the top-most root location where possible, as it does not limit the permissions granted. |
| `--name` | string | Required name of this permission group, unique within its organisational location. |
| `--roles` | list, repeat flag | List of global Role IDs that define this permission group's permissions; an empty list grants no Role permissions. |
| `--added-roles` | list, repeat flag | IDs added to the Roles relationship. |
| `--removed-roles` | list, repeat flag | IDs removed from the Roles relationship. |
| `--users` | list, repeat flag | List of User IDs assigned to this permission group; an empty list assigns the group to no users, and an update replaces the complete assignment list. |
| `--added-users` | list, repeat flag | IDs added to the Users relationship. |
| `--removed-users` | list, repeat flag | IDs removed from the Users relationship. |

**List properties (only returned by `get`, not by `list`):** `Roles`, `AddedRoles`, `RemovedRoles`, `Users`, `AddedUsers`, `RemovedUsers`

<!-- END:GENERATED entity=UserRoles -->
