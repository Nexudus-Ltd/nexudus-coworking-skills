# BasketSessions

<!-- BEGIN:GENERATED entity=BasketSessions -->

A **BasketSession** is an internal entity that temporarily stores basket items while a customer is checking out on the Members Portal. It is not intended for direct use via the API or CLI.

BasketSessions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus basketsessions list --agent` | List all basketsessions |
| `nexudus basketsessions list --id <id> --agent` | Filter by single ID |
| `nexudus basketsessions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus basketsessions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus basketsessions list --session-id <value> --agent` | Filter basketsessions by properties |
| `nexudus basketsessions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus basketsessions get <id> --agent` | Get single basketsession |
| `nexudus basketsessions create --business-id <value> --session-id <value> --agent` | Create basketsession |
| `nexudus basketsessions update <id> --name "New Name" --agent` | Update basketsession |
| `nexudus basketsessions delete <id> --yes --agent` | Delete basketsession (no prompt) |

#### BasketSession list filter options

`--business-id`, `--session-id`, `--json-contents`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### BasketSession create options

`--business-id` (required), `--session-id` (required), `--json-contents`

#### BasketSession update options

`--business-id`, `--session-id`, `--json-contents`

### BasketSession (key fields)

`Id`, `SessionId`

<!-- END:GENERATED entity=BasketSessions -->
