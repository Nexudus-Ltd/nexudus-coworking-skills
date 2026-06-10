# Languages

<!-- BEGIN:GENERATED entity=Languages -->

A **Language** represents a supported language in the system. Languages are used for localising the user interface, email templates, and customer-facing content.

Languages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus languages list --agent` | List all languages |
| `nexudus languages list --id <id> --agent` | Filter by single ID |
| `nexudus languages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus languages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus languages list --business-id <value> --name <value> --agent` | Filter languages by properties |
| `nexudus languages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus languages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus languages get <id> --agent` | Get single language |
| `nexudus languages create --business-id <value> --name <value> --culture <value> --display-order <value> --agent` | Create language |
| `nexudus languages update <id> --name "New Name" --agent` | Update language |
| `nexudus languages delete <id> --yes --agent` | Delete language (no prompt) |

#### Language list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this language |
| `--culture` | string | The culture value for this language |
| `--active` | bool | Whether this language is currently active |
| `--display-order` | int | The display order value for this language |
| `--from-display-order` | range | |
| `--to-display-order` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Language sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Language create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this language |
| `--culture` | string, required | The culture value for this language |
| `--active` | bool | Whether this language is currently active |
| `--display-order` | int, required | The display order value for this language |

#### Language update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this language |
| `--culture` | string | The culture value for this language |
| `--active` | bool | Whether this language is currently active |
| `--display-order` | int | The display order value for this language |

<!-- END:GENERATED entity=Languages -->
