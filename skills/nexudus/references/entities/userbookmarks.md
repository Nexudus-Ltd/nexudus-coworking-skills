# UserBookmarks

<!-- BEGIN:GENERATED entity=UserBookmarks -->

A **UserBookmark** represents a saved shortcut or favourite link created by an administrator for quick access to frequently used pages or records in the admin panel.

UserBookmarks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus userbookmarks list --agent` | List all userbookmarks |
| `nexudus userbookmarks list --id <id> --agent` | Filter by single ID |
| `nexudus userbookmarks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus userbookmarks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus userbookmarks list --user-id <value> --entity-id <value> --agent` | Filter userbookmarks by properties |
| `nexudus userbookmarks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus userbookmarks list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus userbookmarks get <id> --agent` | Get single userbookmark |
| `nexudus userbookmarks create --user-id <value> --entity-id <value> --name <value> --entity-url <value> --agent` | Create userbookmark |
| `nexudus userbookmarks update <id> --name "New Name" --agent` | Update userbookmark |
| `nexudus userbookmarks delete <id> --yes --agent` | Delete userbookmark (no prompt) |

#### UserBookmark list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--user-id` | long | ID of the user linked to this record |
| `--entity-id` | int | ID of the entity associated with this record |
| `--from-entity-id` | range | |
| `--to-entity-id` | range | |
| `--name` | string | The name value for this user bookmark |
| `--entity-url` | string | The entity url value for this user bookmark |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### UserBookmark sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### UserBookmark create options

| Option | Type | Description |
| --- | --- | --- |
| `--user-id` | long, required | ID of the user linked to this record |
| `--entity-id` | int, required | ID of the entity associated with this record |
| `--name` | string, required | The name value for this user bookmark |
| `--entity-url` | string, required | The entity url value for this user bookmark |

#### UserBookmark update options

| Option | Type | Description |
| --- | --- | --- |
| `--user-id` | long | ID of the user linked to this record |
| `--entity-id` | int | ID of the entity associated with this record |
| `--name` | string | The name value for this user bookmark |
| `--entity-url` | string | The entity url value for this user bookmark |

<!-- END:GENERATED entity=UserBookmarks -->
