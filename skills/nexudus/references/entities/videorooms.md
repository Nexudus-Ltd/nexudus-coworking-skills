# VideoRooms

<!-- BEGIN:GENERATED entity=VideoRooms -->

A **VideoRoom** represents a virtual meeting room for video conferencing. Video rooms enable online meetings between members and can be integrated with booking resources.

VideoRooms support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus videorooms list --agent` | List all videorooms |
| `nexudus videorooms list --id <id> --agent` | Filter by single ID |
| `nexudus videorooms list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus videorooms list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus videorooms list --business-id <value> --name <value> --agent` | Filter videorooms by properties |
| `nexudus videorooms list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus videorooms list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus videorooms get <id> --agent` | Get single videoroom |
| `nexudus videorooms create --business-id <value> --name <value> --number-of-participants <value> --agent` | Create videoroom |
| `nexudus videorooms update <id> --name "New Name" --agent` | Update videoroom |
| `nexudus videorooms delete <id> --yes --agent` | Delete videoroom (no prompt) |

#### VideoRoom list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this video room |
| `--description` | string | Free-text description of this video room |
| `--image-file-name` | string | Current file name of the image (read-only; upload via the corresponding URL field) |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--number-of-participants` | int | The number of participants value for this video room |
| `--from-number-of-participants` | range | |
| `--to-number-of-participants` | range | |
| `--active` | bool | Whether this video room is currently active |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### VideoRoom sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### VideoRoom create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this video room |
| `--description` | string | Free-text description of this video room |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--number-of-participants` | int, required | The number of participants value for this video room |
| `--active` | bool | Whether this video room is currently active |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |

#### VideoRoom update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this video room |
| `--description` | string | Free-text description of this video room |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--number-of-participants` | int | The number of participants value for this video room |
| `--active` | bool | Whether this video room is currently active |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |

<!-- END:GENERATED entity=VideoRooms -->
