# CommunityThreadFiles

<!-- BEGIN:GENERATED entity=CommunityThreadFiles -->

CommunityThreadFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreadfiles list --agent` | List all communitythreadfiles |
| `nexudus communitythreadfiles list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreadfiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreadfiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreadfiles list --community-thread-id <value> --name <value> --agent` | Filter communitythreadfiles by properties |
| `nexudus communitythreadfiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreadfiles get <id> --agent` | Get single communitythreadfile |
| `nexudus communitythreadfiles create --community-thread-id <value> --agent` | Create communitythreadfile |
| `nexudus communitythreadfiles update <id> --name "New Name" --agent` | Update communitythreadfile |
| `nexudus communitythreadfiles delete <id> --yes --agent` | Delete communitythreadfile (no prompt) |

#### CommunityThreadFile list filter options

`--community-thread-id`, `--name`, `--description`, `--new-file-data-url`, `--clear-file-data`

#### CommunityThreadFile create options

`--community-thread-id` (required), `--name`, `--description`, `--new-file-data-url`, `--clear-file-data`

#### CommunityThreadFile update options

`--community-thread-id`, `--name`, `--description`, `--new-file-data-url`, `--clear-file-data`

<!-- END:GENERATED entity=CommunityThreadFiles -->
