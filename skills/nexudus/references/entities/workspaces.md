# Workspaces

<!-- BEGIN:GENERATED entity=Workspaces -->

A **Workspace** represents a collaborative workspace or project area where team members can share files, communicate, and coordinate work within the platform.

Workspaces support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus workspaces list --agent` | List all workspaces |
| `nexudus workspaces list --id <id> --agent` | Filter by single ID |
| `nexudus workspaces list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus workspaces list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus workspaces list --business-id <value> --administrator-id <value> --agent` | Filter workspaces by properties |
| `nexudus workspaces list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus workspaces get <id> --agent` | Get single workspace |
| `nexudus workspaces create --business-id <value> --administrator-id <value> --name <value> --agent` | Create workspace |
| `nexudus workspaces update <id> --name "New Name" --agent` | Update workspace |
| `nexudus workspaces delete <id> --yes --agent` | Delete workspace (no prompt) |

#### Workspace list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--administrator-id` | long | ID of the administrator linked to this record |
| `--name` | string | The name value for this workspace |
| `--visible-in-my-spaces` | bool | Whether visible in my spaces is enabled |
| `--visible-by-everyone` | bool | Whether visible by everyone is enabled |
| `--archived` | bool | Whether this workspace is archived and hidden from active lists |
| `--description` | string | Free-text description of this workspace |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Workspace create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--administrator-id` | long, required | ID of the administrator linked to this record |
| `--name` | string, required | The name value for this workspace |
| `--visible-in-my-spaces` | bool | Whether visible in my spaces is enabled |
| `--visible-by-everyone` | bool | Whether visible by everyone is enabled |
| `--archived` | bool | Whether this workspace is archived and hidden from active lists |
| `--description` | string | Free-text description of this workspace |
| `--members` | list, repeat flag | List of members linked to this record |
| `--added-members` | list, repeat flag | The added members value for this workspace |
| `--removed-members` | list, repeat flag | The removed members value for this workspace |

#### Workspace update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--administrator-id` | long | ID of the administrator linked to this record |
| `--name` | string | The name value for this workspace |
| `--visible-in-my-spaces` | bool | Whether visible in my spaces is enabled |
| `--visible-by-everyone` | bool | Whether visible by everyone is enabled |
| `--archived` | bool | Whether this workspace is archived and hidden from active lists |
| `--description` | string | Free-text description of this workspace |
| `--members` | list, repeat flag | List of members linked to this record |
| `--added-members` | list, repeat flag | The added members value for this workspace |
| `--removed-members` | list, repeat flag | The removed members value for this workspace |

**List properties (only returned by `get`, not by `list`):** `Members`, `AddedMembers`, `RemovedMembers`

<!-- END:GENERATED entity=Workspaces -->
