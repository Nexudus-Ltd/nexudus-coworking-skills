# Workspaces

<!-- BEGIN:GENERATED entity=Workspaces -->

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

`--business-id`, `--administrator-id`, `--name`, `--visible-in-my-spaces`, `--visible-by-everyone`, `--archived`, `--description`

#### Workspace create options

`--business-id` (required), `--administrator-id` (required), `--name` (required), `--visible-in-my-spaces`, `--visible-by-everyone`, `--archived`, `--description`, `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag)

#### Workspace update options

`--business-id`, `--administrator-id`, `--name`, `--visible-in-my-spaces`, `--visible-by-everyone`, `--archived`, `--description`, `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Members`, `AddedMembers`, `RemovedMembers`

<!-- END:GENERATED entity=Workspaces -->
