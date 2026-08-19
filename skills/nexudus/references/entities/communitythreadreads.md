# CommunityThreadReads

<!-- BEGIN:GENERATED entity=CommunityThreadReads -->

A CommunityThreadRead records that a user has read the initial post in a private Discussion Board conversation.

CommunityThreadReads support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreadreads list --agent` | List all communitythreadreads |
| `nexudus communitythreadreads list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreadreads list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreadreads list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreadreads list --thread-id <value> --user-id <value> --agent` | Filter communitythreadreads by properties |
| `nexudus communitythreadreads list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreadreads list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitythreadreads get <id> --agent` | Get single communitythreadread |
| `nexudus communitythreadreads create --thread-id <value> --user-id <value> --read-on <value> --agent` | Create communitythreadread |
| `nexudus communitythreadreads update <id> --name "New Name" --agent` | Update communitythreadread |
| `nexudus communitythreadreads delete <id> --yes --agent` | Delete communitythreadread (no prompt) |

#### CommunityThreadRead list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation read by the user |
| `--user-id` | long | ID of the user who read the conversation |
| `--read-on` | DateTime | Date and time when the user last read the conversation |
| `--from-read-on` | range | |
| `--to-read-on` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityThreadRead sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityThreadRead create options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long, required | ID of the conversation read by the user |
| `--user-id` | long, required | ID of the user who read the conversation |
| `--read-on` | DateTime, required | Date and time when the user last read the conversation |

#### CommunityThreadRead update options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation read by the user |
| `--user-id` | long | ID of the user who read the conversation |
| `--read-on` | DateTime | Date and time when the user last read the conversation |

<!-- END:GENERATED entity=CommunityThreadReads -->
