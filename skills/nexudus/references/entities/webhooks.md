# WebHooks

<!-- BEGIN:GENERATED entity=WebHooks -->

WebHooks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus webhooks list --agent` | List all webhooks |
| `nexudus webhooks list --id <id> --agent` | Filter by single ID |
| `nexudus webhooks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus webhooks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus webhooks list --business-id <value> --name <value> --agent` | Filter webhooks by properties |
| `nexudus webhooks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus webhooks get <id> --agent` | Get single webhook |
| `nexudus webhooks create --business-id <value> --name <value> --u-r-l <value> --agent` | Create webhook |
| `nexudus webhooks update <id> --name "New Name" --agent` | Update webhook |
| `nexudus webhooks delete <id> --yes --agent` | Delete webhook (no prompt) |

#### WebHook list filter options

`--business-id`, `--name`, `--action`, `--description`, `--u-r-l`, `--active`

#### WebHook create options

`--business-id` (required), `--name` (required), `--action`, `--description`, `--u-r-l` (required), `--active`

#### WebHook update options

`--business-id`, `--name`, `--action`, `--description`, `--u-r-l`, `--active`

<!-- END:GENERATED entity=WebHooks -->
