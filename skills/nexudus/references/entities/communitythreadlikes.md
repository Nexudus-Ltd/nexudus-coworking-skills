# CommunityThreadLikes

<!-- BEGIN:GENERATED entity=CommunityThreadLikes -->

A **CommunityThreadLike** records a like placed by a user on a `CommunityThread` conversation on the Discussion Board. Each record represents a single like from one user on one conversation.

CommunityThreadLikes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreadlikes list --agent` | List all communitythreadlikes |
| `nexudus communitythreadlikes list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreadlikes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreadlikes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreadlikes list --thread-id <value> --user-id <value> --agent` | Filter communitythreadlikes by properties |
| `nexudus communitythreadlikes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreadlikes get <id> --agent` | Get single communitythreadlike |
| `nexudus communitythreadlikes create --thread-id <value> --user-id <value> --agent` | Create communitythreadlike |
| `nexudus communitythreadlikes update <id> --name "New Name" --agent` | Update communitythreadlike |
| `nexudus communitythreadlikes delete <id> --yes --agent` | Delete communitythreadlike (no prompt) |

#### CommunityThreadLike list filter options

`--thread-id`, `--user-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CommunityThreadLike create options

`--thread-id` (required), `--user-id` (required)

#### CommunityThreadLike update options

`--thread-id`, `--user-id`

<!-- END:GENERATED entity=CommunityThreadLikes -->
