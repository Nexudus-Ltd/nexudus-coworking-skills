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

`--business-id` (long), `--administrator-id` (long), `--name`, `--visible-in-my-spaces` (bool), `--visible-by-everyone` (bool), `--archived` (bool), `--description`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Workspace create options

`--business-id` (long, required), `--administrator-id` (long, required), `--name` (required), `--visible-in-my-spaces` (bool), `--visible-by-everyone` (bool), `--archived` (bool), `--description`, `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag)

#### Workspace update options

`--business-id` (long), `--administrator-id` (long), `--name`, `--visible-in-my-spaces` (bool), `--visible-by-everyone` (bool), `--archived` (bool), `--description`, `--members` (list, repeat flag), `--added-members` (list, repeat flag), `--removed-members` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Members`, `AddedMembers`, `RemovedMembers`

<!-- END:GENERATED entity=Workspaces -->
