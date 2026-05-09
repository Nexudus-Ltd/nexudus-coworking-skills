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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--culture` | string |  |
| `--active` | bool |  |
| `--display-order` | int |  |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Language create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--culture` | string, required |  |
| `--active` | bool |  |
| `--display-order` | int, required |  |

#### Language update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--culture` | string |  |
| `--active` | bool |  |
| `--display-order` | int |  |

<!-- END:GENERATED entity=Languages -->
