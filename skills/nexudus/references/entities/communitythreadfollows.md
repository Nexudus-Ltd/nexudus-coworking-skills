# CommunityThreadFollows

<!-- BEGIN:GENERATED entity=CommunityThreadFollows -->

A **CommunityThreadFollow** records a user following a `CommunityThread` conversation on the Discussion Board. Followers receive notifications when new messages are posted. Users automatically start following a conversation when they are mentioned in it.

CommunityThreadFollows support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreadfollows list --agent` | List all communitythreadfollows |
| `nexudus communitythreadfollows list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreadfollows list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreadfollows list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreadfollows list --thread-id <value> --user-id <value> --agent` | Filter communitythreadfollows by properties |
| `nexudus communitythreadfollows list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreadfollows get <id> --agent` | Get single communitythreadfollow |
| `nexudus communitythreadfollows create --thread-id <value> --user-id <value> --agent` | Create communitythreadfollow |
| `nexudus communitythreadfollows update <id> --name "New Name" --agent` | Update communitythreadfollow |
| `nexudus communitythreadfollows delete <id> --yes --agent` | Delete communitythreadfollow (no prompt) |

#### CommunityThreadFollow list filter options

`--thread-id` (long), `--user-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CommunityThreadFollow create options

`--thread-id` (long, required), `--user-id` (long, required)

#### CommunityThreadFollow update options

`--thread-id` (long), `--user-id` (long)

<!-- END:GENERATED entity=CommunityThreadFollows -->
