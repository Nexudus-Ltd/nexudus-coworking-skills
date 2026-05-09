# UiModules

<!-- BEGIN:GENERATED entity=UiModules -->

UiModules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus uimodules list --agent` | List all uimodules |
| `nexudus uimodules list --id <id> --agent` | Filter by single ID |
| `nexudus uimodules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus uimodules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus uimodules list --business-id <value> --name <value> --agent` | Filter uimodules by properties |
| `nexudus uimodules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus uimodules get <id> --agent` | Get single uimodule |
| `nexudus uimodules create --business-id <value> --name <value> --access-url <value> --icon <value> --agent` | Create uimodule |
| `nexudus uimodules update <id> --name "New Name" --agent` | Update uimodule |
| `nexudus uimodules delete <id> --yes --agent` | Delete uimodule (no prompt) |

#### UiModule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--access-url` | string |  |
| `--icon` | string |  |
| `--active` | bool |  |
| `--shared-secret` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### UiModule create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--access-url` | string, required |  |
| `--icon` | string, required |  |
| `--active` | bool |  |
| `--shared-secret` | string |  |

#### UiModule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--access-url` | string |  |
| `--icon` | string |  |
| `--active` | bool |  |
| `--shared-secret` | string |  |

<!-- END:GENERATED entity=UiModules -->
