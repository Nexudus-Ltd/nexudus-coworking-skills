# UserRoles

<!-- BEGIN:GENERATED entity=UserRoles -->

UserRoles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus userroles list --agent` | List all userroles |
| `nexudus userroles list --id <id> --agent` | Filter by single ID |
| `nexudus userroles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus userroles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus userroles list --business-id <value> --name <value> --agent` | Filter userroles by properties |
| `nexudus userroles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus userroles get <id> --agent` | Get single userrole |
| `nexudus userroles create --business-id <value> --name <value> --agent` | Create userrole |
| `nexudus userroles update <id> --name "New Name" --agent` | Update userrole |
| `nexudus userroles delete <id> --yes --agent` | Delete userrole (no prompt) |

#### UserRole list filter options

`--business-id`, `--name`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### UserRole create options

`--business-id` (required), `--name` (required), `--roles` (list, repeat flag), `--added-roles` (list, repeat flag), `--removed-roles` (list, repeat flag), `--users` (list, repeat flag), `--added-users` (list, repeat flag), `--removed-users` (list, repeat flag)

#### UserRole update options

`--business-id`, `--name`, `--roles` (list, repeat flag), `--added-roles` (list, repeat flag), `--removed-roles` (list, repeat flag), `--users` (list, repeat flag), `--added-users` (list, repeat flag), `--removed-users` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Roles`, `AddedRoles`, `RemovedRoles`, `Users`, `AddedUsers`, `RemovedUsers`

<!-- END:GENERATED entity=UserRoles -->
