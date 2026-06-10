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
| `nexudus communitythreadlikes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitythreadlikes get <id> --agent` | Get single communitythreadlike |
| `nexudus communitythreadlikes create --thread-id <value> --user-id <value> --agent` | Create communitythreadlike |
| `nexudus communitythreadlikes update <id> --name "New Name" --agent` | Update communitythreadlike |
| `nexudus communitythreadlikes delete <id> --yes --agent` | Delete communitythreadlike (no prompt) |

#### CommunityThreadLike list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation that was liked |
| `--user-id` | long | ID of the user who liked the conversation |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityThreadLike sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityThreadLike create options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long, required | ID of the conversation that was liked |
| `--user-id` | long, required | ID of the user who liked the conversation |

#### CommunityThreadLike update options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation that was liked |
| `--user-id` | long | ID of the user who liked the conversation |

<!-- END:GENERATED entity=CommunityThreadLikes -->
