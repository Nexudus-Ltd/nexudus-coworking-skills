# CommunityMessageReads

<!-- BEGIN:GENERATED entity=CommunityMessageReads -->

A CommunityMessageRead records that a user has read an individual message in a private Discussion Board conversation.

CommunityMessageReads support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitymessagereads list --agent` | List all communitymessagereads |
| `nexudus communitymessagereads list --id <id> --agent` | Filter by single ID |
| `nexudus communitymessagereads list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitymessagereads list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitymessagereads list --message-id <value> --user-id <value> --agent` | Filter communitymessagereads by properties |
| `nexudus communitymessagereads list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitymessagereads list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitymessagereads get <id> --agent` | Get single communitymessageread |
| `nexudus communitymessagereads create --message-id <value> --user-id <value> --read-on <value> --agent` | Create communitymessageread |
| `nexudus communitymessagereads update <id> --name "New Name" --agent` | Update communitymessageread |
| `nexudus communitymessagereads delete <id> --yes --agent` | Delete communitymessageread (no prompt) |

#### CommunityMessageRead list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--message-id` | long | ID of the message read by the user |
| `--user-id` | long | ID of the user who read the message |
| `--read-on` | DateTime | Date and time when the user read the message |
| `--from-read-on` | range | |
| `--to-read-on` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityMessageRead sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityMessageRead create options

| Option | Type | Description |
| --- | --- | --- |
| `--message-id` | long, required | ID of the message read by the user |
| `--user-id` | long, required | ID of the user who read the message |
| `--read-on` | DateTime, required | Date and time when the user read the message |

#### CommunityMessageRead update options

| Option | Type | Description |
| --- | --- | --- |
| `--message-id` | long | ID of the message read by the user |
| `--user-id` | long | ID of the user who read the message |
| `--read-on` | DateTime | Date and time when the user read the message |

<!-- END:GENERATED entity=CommunityMessageReads -->
