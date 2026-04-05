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

`--subject`, `--client-id`, `--expires-on`, `--from-expires-on` (range), `--to-expires-on` (range), `--protected-ticket`, `--ticket-hash`, `--ticket-salt`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### RefreshToken create options

`--subject` (required), `--client-id` (required), `--expires-on` (required), `--protected-ticket` (required), `--ticket-hash` (required), `--ticket-salt` (required)

#### RefreshToken update options

`--subject`, `--client-id`, `--expires-on`, `--protected-ticket`, `--ticket-hash`, `--ticket-salt`

<!-- END:GENERATED entity=RefreshTokens -->
