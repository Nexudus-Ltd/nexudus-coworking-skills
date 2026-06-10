# PlatformChangeMessages

<!-- BEGIN:GENERATED entity=PlatformChangeMessages -->

A **PlatformChangeMessage** represents a platform update notification or changelog entry informing administrators about new features, fixes, or changes to the system.

PlatformChangeMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus platformchangemessages list --agent` | List all platformchangemessages |
| `nexudus platformchangemessages list --id <id> --agent` | Filter by single ID |
| `nexudus platformchangemessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus platformchangemessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus platformchangemessages list --title <value> --description-english <value> --agent` | Filter platformchangemessages by properties |
| `nexudus platformchangemessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus platformchangemessages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus platformchangemessages get <id> --agent` | Get single platformchangemessage |
| `nexudus platformchangemessages create --title <value> --agent` | Create platformchangemessage |
| `nexudus platformchangemessages update <id> --name "New Name" --agent` | Update platformchangemessage |
| `nexudus platformchangemessages delete <id> --yes --agent` | Delete platformchangemessage (no prompt) |

#### PlatformChangeMessage list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--title` | string | The title value for this platform change message |
| `--description-english` | string | The description english value for this platform change message |
| `--description-spanish` | string | The description spanish value for this platform change message |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### PlatformChangeMessage sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` descending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (descending).

#### PlatformChangeMessage create options

| Option | Type | Description |
| --- | --- | --- |
| `--title` | string, required | The title value for this platform change message |
| `--description-english` | string | The description english value for this platform change message |
| `--description-spanish` | string | The description spanish value for this platform change message |

#### PlatformChangeMessage update options

| Option | Type | Description |
| --- | --- | --- |
| `--title` | string | The title value for this platform change message |
| `--description-english` | string | The description english value for this platform change message |
| `--description-spanish` | string | The description spanish value for this platform change message |

<!-- END:GENERATED entity=PlatformChangeMessages -->
