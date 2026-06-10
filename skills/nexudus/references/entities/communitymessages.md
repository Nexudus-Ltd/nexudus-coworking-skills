# CommunityMessages

<!-- BEGIN:GENERATED entity=CommunityMessages -->

A **CommunityMessage** is an individual reply posted within a `CommunityThread` conversation on the Discussion Board. Admins and customers with a customer account can add messages to any conversation to help others or share information.

Admins can delete any message; customers can only delete their own.

CommunityMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitymessages list --agent` | List all communitymessages |
| `nexudus communitymessages list --id <id> --agent` | Filter by single ID |
| `nexudus communitymessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitymessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitymessages list --message <value> --agent` | Filter communitymessages by properties |
| `nexudus communitymessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitymessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitymessages get <id> --agent` | Get single communitymessage |
| `nexudus communitymessages create --community-thread-id <value> --user-id <value> --agent` | Create communitymessage |
| `nexudus communitymessages update <id> --name "New Name" --agent` | Update communitymessage |
| `nexudus communitymessages delete <id> --yes --agent` | Delete communitymessage (no prompt) |

#### CommunityMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--community-thread-id` | long | ID of the conversation this message belongs to |
| `--user-id` | long | ID of the user account that posted this message |
| `--coworker-id` | long | ID of the customer profile that posted this message |
| `--message` | string | Body text of the message |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--community-thread-id` | long, required | ID of the conversation this message belongs to |
| `--user-id` | long, required | ID of the user account that posted this message |
| `--coworker-id` | long | ID of the customer profile that posted this message |
| `--message` | string | Body text of the message |

#### CommunityMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--community-thread-id` | long | ID of the conversation this message belongs to |
| `--user-id` | long | ID of the user account that posted this message |
| `--coworker-id` | long | ID of the customer profile that posted this message |
| `--message` | string | Body text of the message |

### CommunityMessage (key fields)

`Id`, `Message`

<!-- END:GENERATED entity=CommunityMessages -->
