# UiModules

<!-- BEGIN:GENERATED entity=UiModules -->

A **UiModule** represents a configurable user interface component or widget that can be enabled or disabled for a location's admin dashboard or member portal.

UiModules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus uimodules list --agent` | List all uimodules |
| `nexudus uimodules list --id <id> --agent` | Filter by single ID |
| `nexudus uimodules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus uimodules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus uimodules list --business-id <value> --name <value> --agent` | Filter uimodules by properties |
| `nexudus uimodules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus uimodules list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus uimodules get <id> --agent` | Get single uimodule |
| `nexudus uimodules create --business-id <value> --name <value> --access-url <value> --icon <value> --agent` | Create uimodule |
| `nexudus uimodules update <id> --name "New Name" --agent` | Update uimodule |
| `nexudus uimodules delete <id> --yes --agent` | Delete uimodule (no prompt) |

#### UiModule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this ui module |
| `--access-url` | string | The access url value for this ui module |
| `--icon` | string | The icon value for this ui module |
| `--active` | bool | Whether this ui module is currently active |
| `--shared-secret` | string | The shared secret value for this ui module |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### UiModule sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### UiModule create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this ui module |
| `--access-url` | string, required | The access url value for this ui module |
| `--icon` | string, required | The icon value for this ui module |
| `--active` | bool | Whether this ui module is currently active |
| `--shared-secret` | string | The shared secret value for this ui module |

#### UiModule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this ui module |
| `--access-url` | string | The access url value for this ui module |
| `--icon` | string | The icon value for this ui module |
| `--active` | bool | Whether this ui module is currently active |
| `--shared-secret` | string | The shared secret value for this ui module |

<!-- END:GENERATED entity=UiModules -->
