# ChatUserMessages

<!-- BEGIN:GENERATED entity=ChatUserMessages -->

Deprecated. Use CommunityThread and CommunityGroups instead.

ChatUserMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus chatusermessages list --agent` | List all chatusermessages |
| `nexudus chatusermessages list --id <id> --agent` | Filter by single ID |
| `nexudus chatusermessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus chatusermessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus chatusermessages list --from-user-id <value> --chat-text <value> --agent` | Filter chatusermessages by properties |
| `nexudus chatusermessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus chatusermessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus chatusermessages get <id> --agent` | Get single chatusermessage |
| `nexudus chatusermessages create --from-user-id <value> --agent` | Create chatusermessage |
| `nexudus chatusermessages update <id> --name "New Name" --agent` | Update chatusermessage |
| `nexudus chatusermessages delete <id> --yes --agent` | Delete chatusermessage (no prompt) |

#### ChatUserMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--from-user-id` | long | ID of the from user linked to this record |
| `--chat-text` | string | The chat text value for this chat user message |
| `--delievered` | bool | Whether delievered is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ChatUserMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ChatUserMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--from-user-id` | long, required | ID of the from user linked to this record |
| `--to-users` | list, repeat flag | List of to users linked to this record |
| `--added-to-users` | list, repeat flag | The added to users value for this chat user message |
| `--removed-to-users` | list, repeat flag | The removed to users value for this chat user message |
| `--chat-text` | string | The chat text value for this chat user message |
| `--delievered` | bool | Whether delievered is enabled |

#### ChatUserMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--from-user-id` | long | ID of the from user linked to this record |
| `--to-users` | list, repeat flag | List of to users linked to this record |
| `--added-to-users` | list, repeat flag | The added to users value for this chat user message |
| `--removed-to-users` | list, repeat flag | The removed to users value for this chat user message |
| `--chat-text` | string | The chat text value for this chat user message |
| `--delievered` | bool | Whether delievered is enabled |

**List properties (only returned by `get`, not by `list`):** `ToUsers`, `AddedToUsers`, `RemovedToUsers`

<!-- END:GENERATED entity=ChatUserMessages -->
