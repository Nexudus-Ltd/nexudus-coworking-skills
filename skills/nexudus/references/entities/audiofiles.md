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

`--business-id` (long), `--name`, `--description`, `--new-audio-url`, `--clear-audio-file` (bool), `--file-size-bytes` (int), `--from-file-size-bytes` (range), `--to-file-size-bytes` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### AudioFile create options

`--business-id` (long, required), `--name` (required), `--description`, `--new-audio-url`, `--clear-audio-file` (bool), `--file-size-bytes` (int)

#### AudioFile update options

`--business-id` (long), `--name`, `--description`, `--new-audio-url`, `--clear-audio-file` (bool), `--file-size-bytes` (int)

### AudioFile (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=AudioFiles -->
