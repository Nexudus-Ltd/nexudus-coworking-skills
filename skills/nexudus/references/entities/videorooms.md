# VideoRooms

<!-- BEGIN:GENERATED entity=VideoRooms -->

VideoRooms support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus videorooms list --agent` | List all videorooms |
| `nexudus videorooms list --id <id> --agent` | Filter by single ID |
| `nexudus videorooms list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus videorooms list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus videorooms list --business-id <value> --name <value> --agent` | Filter videorooms by properties |
| `nexudus videorooms list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus videorooms get <id> --agent` | Get single videoroom |
| `nexudus videorooms create --business-id <value> --name <value> --number-of-participants <value> --agent` | Create videoroom |
| `nexudus videorooms update <id> --name "New Name" --agent` | Update videoroom |
| `nexudus videorooms delete <id> --yes --agent` | Delete videoroom (no prompt) |

#### VideoRoom list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--description` | string |  |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--number-of-participants` | int |  |
| `--from-number-of-participants` | range | |
| `--to-number-of-participants` | range | |
| `--active` | bool |  |
| `--only-for-contacts` | bool |  |
| `--only-for-members` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### VideoRoom create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--description` | string |  |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--number-of-participants` | int, required |  |
| `--active` | bool |  |
| `--only-for-contacts` | bool |  |
| `--only-for-members` | bool |  |

#### VideoRoom update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--description` | string |  |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--number-of-participants` | int |  |
| `--active` | bool |  |
| `--only-for-contacts` | bool |  |
| `--only-for-members` | bool |  |

<!-- END:GENERATED entity=VideoRooms -->
