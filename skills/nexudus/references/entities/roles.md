# Roles

<!-- BEGIN:GENERATED entity=Roles -->

A **Role** defines a set of permissions that can be assigned to administrators. Roles control what areas of the system a user can access and what actions they can perform.

Roles support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus roles list --agent` | List all roles |
| `nexudus roles list --id <id> --agent` | Filter by single ID |
| `nexudus roles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus roles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus roles list --name <value> --agent` | Filter roles by properties |
| `nexudus roles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus roles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus roles get <id> --agent` | Get single role |

#### Role list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | The name value for this role |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Role sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

**List properties (only returned by `get`, not by `list`):** `UserRoles`, `AddedUserRoles`, `RemovedUserRoles`

<!-- END:GENERATED entity=Roles -->
