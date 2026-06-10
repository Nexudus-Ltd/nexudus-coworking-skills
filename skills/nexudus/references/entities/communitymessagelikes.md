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
| `nexudus communitymessagelikes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitymessagelikes get <id> --agent` | Get single communitymessagelike |
| `nexudus communitymessagelikes create --message-id <value> --user-id <value> --agent` | Create communitymessagelike |
| `nexudus communitymessagelikes update <id> --name "New Name" --agent` | Update communitymessagelike |
| `nexudus communitymessagelikes delete <id> --yes --agent` | Delete communitymessagelike (no prompt) |

#### CommunityMessageLike list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--message-id` | long | ID of the message that was liked |
| `--user-id` | long | ID of the user who liked the message |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityMessageLike sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityMessageLike create options

| Option | Type | Description |
| --- | --- | --- |
| `--message-id` | long, required | ID of the message that was liked |
| `--user-id` | long, required | ID of the user who liked the message |

#### CommunityMessageLike update options

| Option | Type | Description |
| --- | --- | --- |
| `--message-id` | long | ID of the message that was liked |
| `--user-id` | long | ID of the user who liked the message |

<!-- END:GENERATED entity=CommunityMessageLikes -->
