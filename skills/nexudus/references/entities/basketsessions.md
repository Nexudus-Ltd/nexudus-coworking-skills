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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--session-id` | string | Unique session identifier linking the basket to the customer's browser session |
| `--json-contents` | string | JSON-serialised basket contents including selected products, quantities, and pricing |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### BasketSession create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--session-id` | string, required | Unique session identifier linking the basket to the customer's browser session |
| `--json-contents` | string | JSON-serialised basket contents including selected products, quantities, and pricing |

#### BasketSession update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--session-id` | string | Unique session identifier linking the basket to the customer's browser session |
| `--json-contents` | string | JSON-serialised basket contents including selected products, quantities, and pricing |

### BasketSession (key fields)

`Id`, `SessionId`

<!-- END:GENERATED entity=BasketSessions -->
