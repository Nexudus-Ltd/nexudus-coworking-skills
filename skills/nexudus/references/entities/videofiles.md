# VideoFiles

<!-- BEGIN:GENERATED entity=VideoFiles -->

VideoFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus videofiles list --agent` | List all videofiles |
| `nexudus videofiles list --id <id> --agent` | Filter by single ID |
| `nexudus videofiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus videofiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus videofiles list --business-id <value> --name <value> --agent` | Filter videofiles by properties |
| `nexudus videofiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus videofiles get <id> --agent` | Get single videofile |
| `nexudus videofiles create --business-id <value> --name <value> --agent` | Create videofile |
| `nexudus videofiles update <id> --name "New Name" --agent` | Update videofile |
| `nexudus videofiles delete <id> --yes --agent` | Delete videofile (no prompt) |

#### VideoFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--description` | string |  |
| `--new-video-url` | string |  |
| `--clear-video-file` | bool |  |
| `--file-size-bytes` | int |  |
| `--from-file-size-bytes` | range | |
| `--to-file-size-bytes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### VideoFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--description` | string |  |
| `--new-video-url` | string |  |
| `--clear-video-file` | bool |  |
| `--file-size-bytes` | int |  |

#### VideoFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--description` | string |  |
| `--new-video-url` | string |  |
| `--clear-video-file` | bool |  |
| `--file-size-bytes` | int |  |

<!-- END:GENERATED entity=VideoFiles -->
