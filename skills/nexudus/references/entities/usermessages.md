# UserMessages

<!-- BEGIN:GENERATED entity=UserMessages -->

A **UserMessage** represents a direct message sent between administrators or from the system to an administrator within the platform.

UserMessages support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus usermessages list --agent` | List all usermessages |
| `nexudus usermessages list --id <id> --agent` | Filter by single ID |
| `nexudus usermessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus usermessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus usermessages list --business-id <value> --header <value> --agent` | Filter usermessages by properties |
| `nexudus usermessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus usermessages get <id> --agent` | Get single usermessage |

#### UserMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--header` | string | The header value for this user message |
| `--body` | string | The body value for this user message |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

**List properties (only returned by `get`, not by `list`):** `ToUsers`, `AddedToUsers`, `RemovedToUsers`

<!-- END:GENERATED entity=UserMessages -->
