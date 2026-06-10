# GlobalChatMessages

<!-- BEGIN:GENERATED entity=GlobalChatMessages -->

A **GlobalChatMessage** represents a message posted in the location-wide chat channel. Global chat messages are visible to all members of a location.

GlobalChatMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus globalchatmessages list --agent` | List all globalchatmessages |
| `nexudus globalchatmessages list --id <id> --agent` | Filter by single ID |
| `nexudus globalchatmessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus globalchatmessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus globalchatmessages list --business-id <value> --from-user-id <value> --agent` | Filter globalchatmessages by properties |
| `nexudus globalchatmessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus globalchatmessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus globalchatmessages get <id> --agent` | Get single globalchatmessage |
| `nexudus globalchatmessages create --business-id <value> --from-user-id <value> --message-text <value> --agent` | Create globalchatmessage |
| `nexudus globalchatmessages update <id> --name "New Name" --agent` | Update globalchatmessage |
| `nexudus globalchatmessages delete <id> --yes --agent` | Delete globalchatmessage (no prompt) |

#### GlobalChatMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--from-user-id` | long | ID of the from user linked to this record |
| `--message-text` | string | The message text value for this global chat message |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### GlobalChatMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### GlobalChatMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--from-user-id` | long, required | ID of the from user linked to this record |
| `--message-text` | string, required | The message text value for this global chat message |

#### GlobalChatMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--from-user-id` | long | ID of the from user linked to this record |
| `--message-text` | string | The message text value for this global chat message |

<!-- END:GENERATED entity=GlobalChatMessages -->
