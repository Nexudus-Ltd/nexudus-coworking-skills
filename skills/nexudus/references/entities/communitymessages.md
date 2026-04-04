# CommunityMessages

<!-- BEGIN:GENERATED entity=CommunityMessages -->

CommunityMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitymessages list --agent` | List all communitymessages |
| `nexudus communitymessages list --id <id> --agent` | Filter by single ID |
| `nexudus communitymessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitymessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitymessages list --community-thread-id <value> --user-id <value> --agent` | Filter communitymessages by properties |
| `nexudus communitymessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitymessages get <id> --agent` | Get single communitymessage |
| `nexudus communitymessages create --community-thread-id <value> --user-id <value> --agent` | Create communitymessage |
| `nexudus communitymessages update <id> --name "New Name" --agent` | Update communitymessage |
| `nexudus communitymessages delete <id> --yes --agent` | Delete communitymessage (no prompt) |

#### CommunityMessage list filter options

`--community-thread-id`, `--user-id`, `--coworker-id`, `--message`

#### CommunityMessage create options

`--community-thread-id` (required), `--user-id` (required), `--coworker-id`, `--message`

#### CommunityMessage update options

`--community-thread-id`, `--user-id`, `--coworker-id`, `--message`

<!-- END:GENERATED entity=CommunityMessages -->
