# CommunityThreadFollows

<!-- BEGIN:GENERATED entity=CommunityThreadFollows -->

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

`--thread-id`, `--user-id`

#### CommunityThreadFollow create options

`--thread-id` (required), `--user-id` (required)

#### CommunityThreadFollow update options

`--thread-id`, `--user-id`

<!-- END:GENERATED entity=CommunityThreadFollows -->
