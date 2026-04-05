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

`--business-id`, `--community-group-id`, `--user-id`, `--coworker-id`, `--subject`, `--message`, `--instant-delivery`, `--tags`, `--private`, `--include-zoom-invite`, `--zoom-event-data`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CommunityThread create options

`--business-id` (required), `--community-group-id`, `--user-id` (required), `--coworker-id`, `--subject` (required), `--message` (required), `--instant-delivery`, `--tags`, `--private`, `--guests` (list, repeat flag), `--added-guests` (list, repeat flag), `--removed-guests` (list, repeat flag), `--include-zoom-invite`, `--zoom-event-data`

#### CommunityThread update options

`--business-id`, `--community-group-id`, `--user-id`, `--coworker-id`, `--subject`, `--message`, `--instant-delivery`, `--tags`, `--private`, `--guests` (list, repeat flag), `--added-guests` (list, repeat flag), `--removed-guests` (list, repeat flag), `--include-zoom-invite`, `--zoom-event-data`

**List properties (only returned by `get`, not by `list`):** `Guests`, `AddedGuests`, `RemovedGuests`

<!-- END:GENERATED entity=CommunityThreads -->
