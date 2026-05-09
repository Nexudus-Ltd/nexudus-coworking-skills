# Roles

<!-- BEGIN:GENERATED entity=Roles -->

Roles support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus roles list --agent` | List all roles |
| `nexudus roles list --id <id> --agent` | Filter by single ID |
| `nexudus roles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus roles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus roles list --name <value> --agent` | Filter roles by properties |
| `nexudus roles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus roles get <id> --agent` | Get single role |

#### Role list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

**List properties (only returned by `get`, not by `list`):** `UserRoles`, `AddedUserRoles`, `RemovedUserRoles`

<!-- END:GENERATED entity=Roles -->
