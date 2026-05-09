# RefreshTokens

<!-- BEGIN:GENERATED entity=RefreshTokens -->

RefreshTokens support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus refreshtokens list --agent` | List all refreshtokens |
| `nexudus refreshtokens list --id <id> --agent` | Filter by single ID |
| `nexudus refreshtokens list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus refreshtokens list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus refreshtokens list --subject <value> --client-id <value> --agent` | Filter refreshtokens by properties |
| `nexudus refreshtokens list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus refreshtokens get <id> --agent` | Get single refreshtoken |
| `nexudus refreshtokens create --subject <value> --client-id <value> --expires-on <value> --protected-ticket <value> --ticket-hash <value> --ticket-salt <value> --agent` | Create refreshtoken |
| `nexudus refreshtokens update <id> --name "New Name" --agent` | Update refreshtoken |
| `nexudus refreshtokens delete <id> --yes --agent` | Delete refreshtoken (no prompt) |

#### RefreshToken list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--subject` | string |  |
| `--client-id` | string |  |
| `--expires-on` | DateTime |  |
| `--from-expires-on` | range | |
| `--to-expires-on` | range | |
| `--protected-ticket` | string |  |
| `--ticket-hash` | string |  |
| `--ticket-salt` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RefreshToken create options

| Option | Type | Description |
| --- | --- | --- |
| `--subject` | string, required |  |
| `--client-id` | string, required |  |
| `--expires-on` | DateTime, required |  |
| `--protected-ticket` | string, required |  |
| `--ticket-hash` | string, required |  |
| `--ticket-salt` | string, required |  |

#### RefreshToken update options

| Option | Type | Description |
| --- | --- | --- |
| `--subject` | string |  |
| `--client-id` | string |  |
| `--expires-on` | DateTime |  |
| `--protected-ticket` | string |  |
| `--ticket-hash` | string |  |
| `--ticket-salt` | string |  |

<!-- END:GENERATED entity=RefreshTokens -->
