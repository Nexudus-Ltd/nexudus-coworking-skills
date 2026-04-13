# CommunityMessageLikes

<!-- BEGIN:GENERATED entity=CommunityMessageLikes -->

A **CommunityMessageLike** records a like placed by a user on an individual `CommunityMessage` reply in a Discussion Board conversation. Each record represents a single like from one user on one message.

CommunityMessageLikes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitymessagelikes list --agent` | List all communitymessagelikes |
| `nexudus communitymessagelikes list --id <id> --agent` | Filter by single ID |
| `nexudus communitymessagelikes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitymessagelikes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitymessagelikes list --message-id <value> --user-id <value> --agent` | Filter communitymessagelikes by properties |
| `nexudus communitymessagelikes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitymessagelikes get <id> --agent` | Get single communitymessagelike |
| `nexudus communitymessagelikes create --message-id <value> --user-id <value> --agent` | Create communitymessagelike |
| `nexudus communitymessagelikes update <id> --name "New Name" --agent` | Update communitymessagelike |
| `nexudus communitymessagelikes delete <id> --yes --agent` | Delete communitymessagelike (no prompt) |

#### CommunityMessageLike list filter options

`--message-id` (long), `--user-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CommunityMessageLike create options

`--message-id` (long, required), `--user-id` (long, required)

#### CommunityMessageLike update options

`--message-id` (long), `--user-id` (long)

<!-- END:GENERATED entity=CommunityMessageLikes -->
