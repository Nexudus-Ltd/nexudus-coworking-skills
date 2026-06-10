# CommunityThreadMutes

<!-- BEGIN:GENERATED entity=CommunityThreadMutes -->

A **CommunityThreadMute** records a user muting a `CommunityThread` conversation on the Discussion Board. Muted users will not receive any notifications for that conversation, even if they are mentioned in it.

CommunityThreadMutes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreadmutes list --agent` | List all communitythreadmutes |
| `nexudus communitythreadmutes list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreadmutes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreadmutes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreadmutes list --thread-id <value> --user-id <value> --agent` | Filter communitythreadmutes by properties |
| `nexudus communitythreadmutes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreadmutes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitythreadmutes get <id> --agent` | Get single communitythreadmute |
| `nexudus communitythreadmutes create --thread-id <value> --user-id <value> --agent` | Create communitythreadmute |
| `nexudus communitythreadmutes update <id> --name "New Name" --agent` | Update communitythreadmute |
| `nexudus communitythreadmutes delete <id> --yes --agent` | Delete communitythreadmute (no prompt) |

#### CommunityThreadMute list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation being muted |
| `--user-id` | long | ID of the user muting the conversation |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityThreadMute sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityThreadMute create options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long, required | ID of the conversation being muted |
| `--user-id` | long, required | ID of the user muting the conversation |

#### CommunityThreadMute update options

| Option | Type | Description |
| --- | --- | --- |
| `--thread-id` | long | ID of the conversation being muted |
| `--user-id` | long | ID of the user muting the conversation |

<!-- END:GENERATED entity=CommunityThreadMutes -->
