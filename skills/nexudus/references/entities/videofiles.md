# VideoFiles

<!-- BEGIN:GENERATED entity=VideoFiles -->

A **VideoFile** represents an uploaded video stored in the system. Video files can be used in courses, community content, or other areas of the platform.

VideoFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus videofiles list --agent` | List all videofiles |
| `nexudus videofiles list --id <id> --agent` | Filter by single ID |
| `nexudus videofiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus videofiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus videofiles list --business-id <value> --name <value> --agent` | Filter videofiles by properties |
| `nexudus videofiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus videofiles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus videofiles get <id> --agent` | Get single videofile |
| `nexudus videofiles create --business-id <value> --name <value> --agent` | Create videofile |
| `nexudus videofiles update <id> --name "New Name" --agent` | Update videofile |
| `nexudus videofiles delete <id> --yes --agent` | Delete videofile (no prompt) |

#### VideoFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this video file |
| `--description` | string | Free-text description of this video file |
| `--new-video-url` | string | URL of a new file to upload as the video |
| `--clear-video-file` | bool | Set to true to remove the current video file |
| `--file-size-bytes` | int | The file size bytes value for this video file |
| `--from-file-size-bytes` | range | |
| `--to-file-size-bytes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### VideoFile sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### VideoFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this video file |
| `--description` | string | Free-text description of this video file |
| `--new-video-url` | string | URL of a new file to upload as the video |
| `--clear-video-file` | bool | Set to true to remove the current video file |
| `--file-size-bytes` | int | The file size bytes value for this video file |

#### VideoFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this video file |
| `--description` | string | Free-text description of this video file |
| `--new-video-url` | string | URL of a new file to upload as the video |
| `--clear-video-file` | bool | Set to true to remove the current video file |
| `--file-size-bytes` | int | The file size bytes value for this video file |

<!-- END:GENERATED entity=VideoFiles -->
