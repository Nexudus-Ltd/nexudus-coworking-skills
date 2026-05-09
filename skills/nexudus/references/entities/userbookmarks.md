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

| Option | Type | Description |
| --- | --- | --- |
| `--user-id` | long |  |
| `--entity-id` | int |  |
| `--from-entity-id` | range | |
| `--to-entity-id` | range | |
| `--name` | string |  |
| `--entity-url` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### UserBookmark create options

| Option | Type | Description |
| --- | --- | --- |
| `--user-id` | long, required |  |
| `--entity-id` | int, required |  |
| `--name` | string, required |  |
| `--entity-url` | string, required |  |

#### UserBookmark update options

| Option | Type | Description |
| --- | --- | --- |
| `--user-id` | long |  |
| `--entity-id` | int |  |
| `--name` | string |  |
| `--entity-url` | string |  |

<!-- END:GENERATED entity=UserBookmarks -->
