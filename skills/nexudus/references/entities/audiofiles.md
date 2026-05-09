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
| `nexudus audiofiles get <id> --agent` | Get single audiofile |
| `nexudus audiofiles create --business-id <value> --name <value> --agent` | Create audiofile |
| `nexudus audiofiles update <id> --name "New Name" --agent` | Update audiofile |
| `nexudus audiofiles delete <id> --yes --agent` | Delete audiofile (no prompt) |

#### AudioFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Name of the audio file |
| `--description` | string | Description of the audio file |
| `--new-audio-url` | string |  |
| `--clear-audio-file` | bool |  |
| `--file-size-bytes` | int | File size in bytes |
| `--from-file-size-bytes` | range | |
| `--to-file-size-bytes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AudioFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required | Name of the audio file |
| `--description` | string | Description of the audio file |
| `--new-audio-url` | string |  |
| `--clear-audio-file` | bool |  |
| `--file-size-bytes` | int | File size in bytes |

#### AudioFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Name of the audio file |
| `--description` | string | Description of the audio file |
| `--new-audio-url` | string |  |
| `--clear-audio-file` | bool |  |
| `--file-size-bytes` | int | File size in bytes |

### AudioFile (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=AudioFiles -->
