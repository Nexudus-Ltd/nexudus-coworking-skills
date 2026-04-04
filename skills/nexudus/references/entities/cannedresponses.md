# CannedResponses

<!-- BEGIN:GENERATED entity=CannedResponses -->

CannedResponses support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus cannedresponses list --agent` | List all cannedresponses |
| `nexudus cannedresponses list --id <id> --agent` | Filter by single ID |
| `nexudus cannedresponses list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus cannedresponses list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus cannedresponses list --business-id <value> --name <value> --agent` | Filter cannedresponses by properties |
| `nexudus cannedresponses list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus cannedresponses get <id> --agent` | Get single cannedresponse |
| `nexudus cannedresponses create --business-id <value> --name <value> --agent` | Create cannedresponse |
| `nexudus cannedresponses update <id> --name "New Name" --agent` | Update cannedresponse |
| `nexudus cannedresponses delete <id> --yes --agent` | Delete cannedresponse (no prompt) |

#### CannedResponse list filter options

`--business-id`, `--name`, `--subject`, `--message-text`

#### CannedResponse create options

`--business-id` (required), `--name` (required), `--subject`, `--message-text`

#### CannedResponse update options

`--business-id`, `--name`, `--subject`, `--message-text`

<!-- END:GENERATED entity=CannedResponses -->
