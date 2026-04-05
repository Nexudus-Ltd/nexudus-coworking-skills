# ChatUserMessages

<!-- BEGIN:GENERATED entity=ChatUserMessages -->

Deprecated. Use CommunityThread and CommunityGroups instead.

ChatUserMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus chatusermessages list --agent` | List all chatusermessages |
| `nexudus chatusermessages list --id <id> --agent` | Filter by single ID |
| `nexudus chatusermessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus chatusermessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus chatusermessages list --from-user-id <value> --chat-text <value> --agent` | Filter chatusermessages by properties |
| `nexudus chatusermessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus chatusermessages get <id> --agent` | Get single chatusermessage |
| `nexudus chatusermessages create --from-user-id <value> --agent` | Create chatusermessage |
| `nexudus chatusermessages update <id> --name "New Name" --agent` | Update chatusermessage |
| `nexudus chatusermessages delete <id> --yes --agent` | Delete chatusermessage (no prompt) |

#### ChatUserMessage list filter options

`--from-user-id`, `--chat-text`, `--delievered`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ChatUserMessage create options

`--from-user-id` (required), `--to-users` (list, repeat flag), `--added-to-users` (list, repeat flag), `--removed-to-users` (list, repeat flag), `--chat-text`, `--delievered`

#### ChatUserMessage update options

`--from-user-id`, `--to-users` (list, repeat flag), `--added-to-users` (list, repeat flag), `--removed-to-users` (list, repeat flag), `--chat-text`, `--delievered`

**List properties (only returned by `get`, not by `list`):** `ToUsers`, `AddedToUsers`, `RemovedToUsers`

<!-- END:GENERATED entity=ChatUserMessages -->
