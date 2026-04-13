# CommunityThreadFiles

<!-- BEGIN:GENERATED entity=CommunityThreadFiles -->

A **CommunityThreadFile** is a file or image attached to a `CommunityThread` conversation on the Discussion Board. When starting a conversation, customers can optionally include a picture or file alongside the opening message.

CommunityThreadFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus communitythreadfiles list --agent` | List all communitythreadfiles |
| `nexudus communitythreadfiles list --id <id> --agent` | Filter by single ID |
| `nexudus communitythreadfiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus communitythreadfiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus communitythreadfiles list --name <value> --agent` | Filter communitythreadfiles by properties |
| `nexudus communitythreadfiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus communitythreadfiles get <id> --agent` | Get single communitythreadfile |
| `nexudus communitythreadfiles create --community-thread-id <value> --agent` | Create communitythreadfile |
| `nexudus communitythreadfiles update <id> --name "New Name" --agent` | Update communitythreadfile |
| `nexudus communitythreadfiles delete <id> --yes --agent` | Delete communitythreadfile (no prompt) |

#### CommunityThreadFile list filter options

`--community-thread-id` (long), `--name`, `--description`, `--new-file-data-url`, `--clear-file-data-file` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CommunityThreadFile create options

`--community-thread-id` (long, required), `--name`, `--description`, `--new-file-data-url`, `--clear-file-data-file` (bool)

#### CommunityThreadFile update options

`--community-thread-id` (long), `--name`, `--description`, `--new-file-data-url`, `--clear-file-data-file` (bool)

### CommunityThreadFile (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=CommunityThreadFiles -->
