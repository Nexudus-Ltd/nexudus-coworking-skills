# UserBookmarks

<!-- BEGIN:GENERATED entity=UserBookmarks -->

UserBookmarks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus userbookmarks list --agent` | List all userbookmarks |
| `nexudus userbookmarks list --id <id> --agent` | Filter by single ID |
| `nexudus userbookmarks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus userbookmarks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus userbookmarks list --user-id <value> --entity-id <value> --agent` | Filter userbookmarks by properties |
| `nexudus userbookmarks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus userbookmarks get <id> --agent` | Get single userbookmark |
| `nexudus userbookmarks create --user-id <value> --entity-id <value> --name <value> --entity-url <value> --agent` | Create userbookmark |
| `nexudus userbookmarks update <id> --name "New Name" --agent` | Update userbookmark |
| `nexudus userbookmarks delete <id> --yes --agent` | Delete userbookmark (no prompt) |

#### UserBookmark list filter options

`--user-id`, `--entity-id`, `--name`, `--entity-url`

#### UserBookmark create options

`--user-id` (required), `--entity-id` (required), `--name` (required), `--entity-url` (required)

#### UserBookmark update options

`--user-id`, `--entity-id`, `--name`, `--entity-url`

<!-- END:GENERATED entity=UserBookmarks -->
