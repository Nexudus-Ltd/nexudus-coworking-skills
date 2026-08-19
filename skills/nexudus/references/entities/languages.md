# Languages

<!-- BEGIN:GENERATED entity=Languages -->

A Language is a location's supported interface and customer-facing content language, identified by its culture code and translation tokens.

Languages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus languages list --agent` | List all languages |
| `nexudus languages list --id <id> --agent` | Filter by single ID |
| `nexudus languages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus languages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus languages list --business-id <value> --business-name <value> --agent` | Filter languages by properties |
| `nexudus languages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus languages list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus languages get <id> --agent` | Get single language |
| `nexudus languages create --business-id <value> --name <value> --culture <value> --display-order <value> --agent` | Create language |
| `nexudus languages update <id> --name "New Name" --agent` | Update language |
| `nexudus languages delete <id> --yes --agent` | Delete language (no prompt) |

#### Language list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this language |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--name` | string | Required display name for this language |
| `--culture` | string | Required unique culture code used to match the language for a request, such as en or es |
| `--active` | bool | Whether this language is included in the location's active language list |
| `--display-order` | int | Integer sort order for this language in the location's active language list; lower values appear first |
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
| `--business-id` | long, required | ID of the location that owns this language |
| `--name` | string, required | Required display name for this language |
| `--culture` | string, required | Required unique culture code used to match the language for a request, such as en or es |
| `--active` | bool | Whether this language is included in the location's active language list |
| `--display-order` | int, required | Integer sort order for this language in the location's active language list; lower values appear first |

#### Language update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this language |
| `--name` | string | Required display name for this language |
| `--culture` | string | Required unique culture code used to match the language for a request, such as en or es |
| `--active` | bool | Whether this language is included in the location's active language list |
| `--display-order` | int | Integer sort order for this language in the location's active language list; lower values appear first |

<!-- END:GENERATED entity=Languages -->
