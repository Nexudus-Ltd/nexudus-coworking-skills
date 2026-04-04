# Languages

<!-- BEGIN:GENERATED entity=Languages -->

Languages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus languages list --agent` | List all languages |
| `nexudus languages list --id <id> --agent` | Filter by single ID |
| `nexudus languages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus languages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus languages list --business-id <value> --name <value> --agent` | Filter languages by properties |
| `nexudus languages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus languages get <id> --agent` | Get single language |
| `nexudus languages create --business-id <value> --name <value> --culture <value> --display-order <value> --agent` | Create language |
| `nexudus languages update <id> --name "New Name" --agent` | Update language |
| `nexudus languages delete <id> --yes --agent` | Delete language (no prompt) |

#### Language list filter options

`--business-id`, `--name`, `--culture`, `--active`, `--display-order`

#### Language create options

`--business-id` (required), `--name` (required), `--culture` (required), `--active`, `--display-order` (required), `--tokens` (list, repeat flag), `--added-tokens` (list, repeat flag), `--removed-tokens` (list, repeat flag)

#### Language update options

`--business-id`, `--name`, `--culture`, `--active`, `--display-order`, `--tokens` (list, repeat flag), `--added-tokens` (list, repeat flag), `--removed-tokens` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Tokens`, `AddedTokens`, `RemovedTokens`

<!-- END:GENERATED entity=Languages -->
