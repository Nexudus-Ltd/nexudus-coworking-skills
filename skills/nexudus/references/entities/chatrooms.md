# ChatRooms

<!-- BEGIN:GENERATED entity=ChatRooms -->

Deprecated. Use CommunityThread and CommunityGroups instead.

ChatRooms support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus chatrooms list --agent` | List all chatrooms |
| `nexudus chatrooms list --id <id> --agent` | Filter by single ID |
| `nexudus chatrooms list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus chatrooms list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus chatrooms list --business-id <value> --name <value> --agent` | Filter chatrooms by properties |
| `nexudus chatrooms list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus chatrooms get <id> --agent` | Get single chatroom |
| `nexudus chatrooms create --business-id <value> --agent` | Create chatroom |
| `nexudus chatrooms update <id> --name "New Name" --agent` | Update chatroom |
| `nexudus chatrooms delete <id> --yes --agent` | Delete chatroom (no prompt) |

#### ChatRoom list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--active` | bool |  |
| `--last-agent-visit` | DateTime |  |
| `--from-last-agent-visit` | range | |
| `--to-last-agent-visit` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ChatRoom create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string |  |
| `--active` | bool |  |
| `--last-agent-visit` | DateTime |  |
| `--users` | list, repeat flag |  |
| `--added-users` | list, repeat flag |  |
| `--removed-users` | list, repeat flag |  |

#### ChatRoom update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--active` | bool |  |
| `--last-agent-visit` | DateTime |  |
| `--users` | list, repeat flag |  |
| `--added-users` | list, repeat flag |  |
| `--removed-users` | list, repeat flag |  |

**List properties (only returned by `get`, not by `list`):** `Users`, `AddedUsers`, `RemovedUsers`

<!-- END:GENERATED entity=ChatRooms -->
