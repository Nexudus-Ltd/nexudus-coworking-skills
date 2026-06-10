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
| `nexudus communitythreadfollows list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitythreadfollows get <id> --agent` | Get single communitythreadfollow |
| `nexudus communitythreadfollows create --thread-id <value> --user-id <value> --agent` | Create communitythreadfollow |
| `nexudus communitythreadfollows update <id> --name "New Name" --agent` | Update communitythreadfollow |
| `nexudus communitythreadfollows delete <id> --yes --agent` | Delete communitythreadfollow (no prompt) |

#### CommunityThreadFollow list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation being followed |
| `--user-id` | long | ID of the user following the conversation |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityThreadFollow sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityThreadFollow create options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long, required | ID of the conversation being followed |
| `--user-id` | long, required | ID of the user following the conversation |

#### CommunityThreadFollow update options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation being followed |
| `--user-id` | long | ID of the user following the conversation |

<!-- END:GENERATED entity=CommunityThreadFollows -->
