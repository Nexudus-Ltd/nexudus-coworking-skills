# AudioFiles

<!-- BEGIN:GENERATED entity=AudioFiles -->

Represents a valid audio file stored in the Nexudus account. These can be used in document templates, newsletters or custom pages in the Members Portal and app.

AudioFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus audiofiles list --agent` | List all audiofiles |
| `nexudus audiofiles list --id <id> --agent` | Filter by single ID |
| `nexudus audiofiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus audiofiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus audiofiles list --name <value> --agent` | Filter audiofiles by properties |
| `nexudus audiofiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus audiofiles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus audiofiles get <id> --agent` | Get single audiofile |
| `nexudus audiofiles create --business-id <value> --name <value> --agent` | Create audiofile |
| `nexudus audiofiles update <id> --name "New Name" --agent` | Update audiofile |
| `nexudus audiofiles delete <id> --yes --agent` | Delete audiofile (no prompt) |

#### AudioFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Name of the audio file |
| `--description` | string | Description of the audio file |
| `--audio-file-name` | string | Current file name of the audio (read-only; upload via the corresponding URL field) |
| `--new-audio-url` | string | URL of a new file to upload as the audio |
| `--clear-audio-file` | bool | Set to true to remove the current audio file |
| `--file-size-bytes` | int | File size in bytes |
| `--from-file-size-bytes` | range | |
| `--to-file-size-bytes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AudioFile sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AudioFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Name of the audio file |
| `--description` | string | Description of the audio file |
| `--new-audio-url` | string | URL of a new file to upload as the audio |
| `--clear-audio-file` | bool | Set to true to remove the current audio file |
| `--file-size-bytes` | int | File size in bytes |

#### AudioFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Name of the audio file |
| `--description` | string | Description of the audio file |
| `--new-audio-url` | string | URL of a new file to upload as the audio |
| `--clear-audio-file` | bool | Set to true to remove the current audio file |
| `--file-size-bytes` | int | File size in bytes |

### AudioFile (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=AudioFiles -->
