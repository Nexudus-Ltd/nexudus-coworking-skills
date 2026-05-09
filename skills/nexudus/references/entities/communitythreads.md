# CommunityThreads

<!-- BEGIN:GENERATED entity=CommunityThreads -->

A **CommunityThread** represents a conversation posted to the Discussion Board. Discussion boards are a community feature that allows customers to communicate on the Members Portal — they can start, follow, like, and reply to conversations, mention other customers, and receive notifications about new messages.

Conversations can be assigned to a group (`CommunityGroupId`) to control who can see and contribute. Conversations not linked to any group are visible to all customers with access to the Discussion Boards page.

Use `Tags` to help customers find relevant conversations. Set `Private` to `true` to limit visibility to only the customers explicitly mentioned in the message. Enable `InstantDelivery` to push notifications to followers immediately rather than waiting for the daily digest.

CommunityThreads support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreads list --agent` | List all communitythreads |
| `nexudus communitythreads list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreads list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreads list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreads list --business-id <value> --community-group-id <value> --agent` | Filter communitythreads by properties |
| `nexudus communitythreads list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreads get <id> --agent` | Get single communitythread |
| `nexudus communitythreads create --business-id <value> --user-id <value> --subject <value> --message <value> --agent` | Create communitythread |
| `nexudus communitythreads update <id> --name "New Name" --agent` | Update communitythread |
| `nexudus communitythreads delete <id> --yes --agent` | Delete communitythread (no prompt) |

#### CommunityThread list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this conversation belongs to |
| `--community-group-id` | long | ID of the group this conversation is assigned to; the group's access level (Public, Restricted, or Private) determines who can see and contribute to it |
| `--user-id` | long | ID of the user account that posted this conversation |
| `--coworker-id` | long | ID of the customer profile that posted this conversation |
| `--subject` | string | Title or topic of the conversation |
| `--message` | string | Body text of the opening message in this conversation |
| `--instant-delivery` | bool | When true, sends notifications to followers immediately after posting instead of waiting for the daily digest |
| `--tags` | string | Comma-separated tags to help customers find this conversation |
| `--private` | bool | When true, the conversation is visible only to customers explicitly mentioned in the message |
| `--include-zoom-invite` | bool | When true, attaches a Zoom meeting invite to this conversation |
| `--zoom-event-data` | string | JSON payload containing Zoom meeting details attached to this conversation |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CommunityThread create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this conversation belongs to |
| `--community-group-id` | long | ID of the group this conversation is assigned to; the group's access level (Public, Restricted, or Private) determines who can see and contribute to it |
| `--user-id` | long, required | ID of the user account that posted this conversation |
| `--coworker-id` | long | ID of the customer profile that posted this conversation |
| `--subject` | string, required | Title or topic of the conversation |
| `--message` | string, required | Body text of the opening message in this conversation |
| `--instant-delivery` | bool | When true, sends notifications to followers immediately after posting instead of waiting for the daily digest |
| `--tags` | string | Comma-separated tags to help customers find this conversation |
| `--private` | bool | When true, the conversation is visible only to customers explicitly mentioned in the message |
| `--guests` | list, repeat flag | IDs of users mentioned or invited as guests in this conversation |
| `--added-guests` | list, repeat flag | User IDs to add as guests (used in partial updates) |
| `--removed-guests` | list, repeat flag | User IDs to remove as guests (used in partial updates) |
| `--include-zoom-invite` | bool | When true, attaches a Zoom meeting invite to this conversation |
| `--zoom-event-data` | string | JSON payload containing Zoom meeting details attached to this conversation |

#### CommunityThread update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this conversation belongs to |
| `--community-group-id` | long | ID of the group this conversation is assigned to; the group's access level (Public, Restricted, or Private) determines who can see and contribute to it |
| `--user-id` | long | ID of the user account that posted this conversation |
| `--coworker-id` | long | ID of the customer profile that posted this conversation |
| `--subject` | string | Title or topic of the conversation |
| `--message` | string | Body text of the opening message in this conversation |
| `--instant-delivery` | bool | When true, sends notifications to followers immediately after posting instead of waiting for the daily digest |
| `--tags` | string | Comma-separated tags to help customers find this conversation |
| `--private` | bool | When true, the conversation is visible only to customers explicitly mentioned in the message |
| `--guests` | list, repeat flag | IDs of users mentioned or invited as guests in this conversation |
| `--added-guests` | list, repeat flag | User IDs to add as guests (used in partial updates) |
| `--removed-guests` | list, repeat flag | User IDs to remove as guests (used in partial updates) |
| `--include-zoom-invite` | bool | When true, attaches a Zoom meeting invite to this conversation |
| `--zoom-event-data` | string | JSON payload containing Zoom meeting details attached to this conversation |

**List properties (only returned by `get`, not by `list`):** `Guests`, `AddedGuests`, `RemovedGuests`

<!-- END:GENERATED entity=CommunityThreads -->
