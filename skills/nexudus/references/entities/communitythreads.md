# CommunityThreads

<!-- BEGIN:GENERATED entity=CommunityThreads -->

A Discussion Board conversation is an opening message with replies that customers can follow; a community group or private guest list controls who can access it.

CommunityThreads support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreads list --agent` | List all communitythreads |
| `nexudus communitythreads list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreads list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreads list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreads list --business-id <value> --community-group-id <value> --agent` | Filter communitythreads by properties |
| `nexudus communitythreads list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreads list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus communitythreads get <id> --agent` | Get single communitythread |
| `nexudus communitythreads create --business-id <value> --user-id <value> --subject <value> --message <value> --agent` | Create communitythread |
| `nexudus communitythreads update <id> --name "New Name" --agent` | Update communitythread |
| `nexudus communitythreads delete <id> --yes --agent` | Delete communitythread (no prompt) |

#### CommunityThread list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this Discussion Board conversation belongs to |
| `--community-group-id` | long | Optional ID of the community group that controls access to this conversation; its Public, Restricted, or Private access level applies in addition to this thread's Private setting |
| `--user-id` | long | ID of the user account that authors this conversation |
| `--coworker-id` | long | Optional ID of the customer profile displayed as the author; when omitted on creation, Nexudus uses the author's matching customer profile at the location |
| `--subject` | string | Required title or topic of the Discussion Board conversation |
| `--message` | string | Required body text of the opening message in this conversation |
| `--instant-delivery` | bool | Whether to notify followers about this new conversation immediately instead of waiting for their scheduled digest |
| `--tags` | string | Comma-separated search tags that help customers find this conversation |
| `--private` | bool | Whether this conversation is visible only to its author and the users in Guests; a private community group also restricts visibility regardless of this setting |
| `--last-message-date` | DateTime | Read-only UTC date and time when this conversation or one of its replies was most recently posted |
| `--from-last-message-date` | range | |
| `--to-last-message-date` | range | |
| `--include-zoom-invite` | bool | Whether to create a Zoom meeting and attach its invite when this conversation is created |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityThread sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CommunityThread create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this Discussion Board conversation belongs to |
| `--community-group-id` | long | Optional ID of the community group that controls access to this conversation; its Public, Restricted, or Private access level applies in addition to this thread's Private setting |
| `--user-id` | long, required | ID of the user account that authors this conversation |
| `--coworker-id` | long | Optional ID of the customer profile displayed as the author; when omitted on creation, Nexudus uses the author's matching customer profile at the location |
| `--subject` | string, required | Required title or topic of the Discussion Board conversation |
| `--message` | string, required | Required body text of the opening message in this conversation |
| `--instant-delivery` | bool | Whether to notify followers about this new conversation immediately instead of waiting for their scheduled digest |
| `--tags` | string | Comma-separated search tags that help customers find this conversation |
| `--private` | bool | Whether this conversation is visible only to its author and the users in Guests; a private community group also restricts visibility regardless of this setting |
| `--guests` | list, repeat flag | List of user IDs allowed to read this thread when Private is true; an assigned community group's members are added automatically when the thread is created |
| `--added-guests` | list, repeat flag | User IDs to add as guests (used in partial updates) |
| `--removed-guests` | list, repeat flag | User IDs to remove as guests (used in partial updates) |
| `--include-zoom-invite` | bool | Whether to create a Zoom meeting and attach its invite when this conversation is created |

#### CommunityThread update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this Discussion Board conversation belongs to |
| `--community-group-id` | long | Optional ID of the community group that controls access to this conversation; its Public, Restricted, or Private access level applies in addition to this thread's Private setting |
| `--user-id` | long | ID of the user account that authors this conversation |
| `--coworker-id` | long | Optional ID of the customer profile displayed as the author; when omitted on creation, Nexudus uses the author's matching customer profile at the location |
| `--subject` | string | Required title or topic of the Discussion Board conversation |
| `--message` | string | Required body text of the opening message in this conversation |
| `--instant-delivery` | bool | Whether to notify followers about this new conversation immediately instead of waiting for their scheduled digest |
| `--tags` | string | Comma-separated search tags that help customers find this conversation |
| `--private` | bool | Whether this conversation is visible only to its author and the users in Guests; a private community group also restricts visibility regardless of this setting |
| `--guests` | list, repeat flag | List of user IDs allowed to read this thread when Private is true; an assigned community group's members are added automatically when the thread is created |
| `--added-guests` | list, repeat flag | User IDs to add as guests (used in partial updates) |
| `--removed-guests` | list, repeat flag | User IDs to remove as guests (used in partial updates) |
| `--include-zoom-invite` | bool | Whether to create a Zoom meeting and attach its invite when this conversation is created |

**List properties (only returned by `get`, not by `list`):** `Guests`, `AddedGuests`, `RemovedGuests`

<!-- END:GENERATED entity=CommunityThreads -->
