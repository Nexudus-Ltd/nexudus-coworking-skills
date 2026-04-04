# GlobalChatMessages

<!-- BEGIN:GENERATED entity=GlobalChatMessages -->

GlobalChatMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus globalchatmessages list --agent` | List all globalchatmessages |
| `nexudus globalchatmessages list --id <id> --agent` | Filter by single ID |
| `nexudus globalchatmessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus globalchatmessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus globalchatmessages list --business-id <value> --from-user-id <value> --agent` | Filter globalchatmessages by properties |
| `nexudus globalchatmessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus globalchatmessages get <id> --agent` | Get single globalchatmessage |
| `nexudus globalchatmessages create --business-id <value> --from-user-id <value> --message-text <value> --agent` | Create globalchatmessage |
| `nexudus globalchatmessages update <id> --name "New Name" --agent` | Update globalchatmessage |
| `nexudus globalchatmessages delete <id> --yes --agent` | Delete globalchatmessage (no prompt) |

#### GlobalChatMessage list filter options

`--business-id`, `--from-user-id`, `--message-text`

#### GlobalChatMessage create options

`--business-id` (required), `--from-user-id` (required), `--message-text` (required)

#### GlobalChatMessage update options

`--business-id`, `--from-user-id`, `--message-text`

<!-- END:GENERATED entity=GlobalChatMessages -->
