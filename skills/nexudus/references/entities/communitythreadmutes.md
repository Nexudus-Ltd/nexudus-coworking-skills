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
| `nexudus communitythreadmutes get <id> --agent` | Get single communitythreadmute |
| `nexudus communitythreadmutes create --thread-id <value> --user-id <value> --agent` | Create communitythreadmute |
| `nexudus communitythreadmutes update <id> --name "New Name" --agent` | Update communitythreadmute |
| `nexudus communitythreadmutes delete <id> --yes --agent` | Delete communitythreadmute (no prompt) |

#### CommunityThreadMute list filter options

`--thread-id` (long), `--user-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CommunityThreadMute create options

`--thread-id` (long, required), `--user-id` (long, required)

#### CommunityThreadMute update options

`--thread-id` (long), `--user-id` (long)

<!-- END:GENERATED entity=CommunityThreadMutes -->
