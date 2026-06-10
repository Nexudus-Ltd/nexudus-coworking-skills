# RefreshTokens

<!-- BEGIN:GENERATED entity=RefreshTokens -->

A **RefreshToken** represents an OAuth refresh token issued to maintain authenticated sessions. Refresh tokens allow clients to obtain new access tokens without re-authentication.

RefreshTokens support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus refreshtokens list --agent` | List all refreshtokens |
| `nexudus refreshtokens list --id <id> --agent` | Filter by single ID |
| `nexudus refreshtokens list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus refreshtokens list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus refreshtokens list --subject <value> --client-id <value> --agent` | Filter refreshtokens by properties |
| `nexudus refreshtokens list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus refreshtokens list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus refreshtokens get <id> --agent` | Get single refreshtoken |
| `nexudus refreshtokens create --subject <value> --client-id <value> --expires-on <value> --protected-ticket <value> --ticket-hash <value> --ticket-salt <value> --agent` | Create refreshtoken |
| `nexudus refreshtokens update <id> --name "New Name" --agent` | Update refreshtoken |
| `nexudus refreshtokens delete <id> --yes --agent` | Delete refreshtoken (no prompt) |

#### RefreshToken list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--subject` | string | The subject value for this refresh token |
| `--client-id` | string | ID of the client associated with this record |
| `--expires-on` | DateTime | Date/time value for expires on |
| `--from-expires-on` | range | |
| `--to-expires-on` | range | |
| `--protected-ticket` | string | The protected ticket value for this refresh token |
| `--ticket-hash` | string | The ticket hash value for this refresh token |
| `--ticket-salt` | string | The ticket salt value for this refresh token |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RefreshToken sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### RefreshToken create options

| Option | Type | Description |
| --- | --- | --- |
| `--subject` | string, required | The subject value for this refresh token |
| `--client-id` | string, required | ID of the client associated with this record |
| `--expires-on` | DateTime, required | Date/time value for expires on |
| `--protected-ticket` | string, required | The protected ticket value for this refresh token |
| `--ticket-hash` | string, required | The ticket hash value for this refresh token |
| `--ticket-salt` | string, required | The ticket salt value for this refresh token |

#### RefreshToken update options

| Option | Type | Description |
| --- | --- | --- |
| `--subject` | string | The subject value for this refresh token |
| `--client-id` | string | ID of the client associated with this record |
| `--expires-on` | DateTime | Date/time value for expires on |
| `--protected-ticket` | string | The protected ticket value for this refresh token |
| `--ticket-hash` | string | The ticket hash value for this refresh token |
| `--ticket-salt` | string | The ticket salt value for this refresh token |

<!-- END:GENERATED entity=RefreshTokens -->
