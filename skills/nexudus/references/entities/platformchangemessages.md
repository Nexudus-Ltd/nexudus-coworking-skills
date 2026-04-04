# PlatformChangeMessages

<!-- BEGIN:GENERATED entity=PlatformChangeMessages -->

PlatformChangeMessages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus platformchangemessages list --agent` | List all platformchangemessages |
| `nexudus platformchangemessages list --id <id> --agent` | Filter by single ID |
| `nexudus platformchangemessages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus platformchangemessages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus platformchangemessages list --title <value> --description-english <value> --agent` | Filter platformchangemessages by properties |
| `nexudus platformchangemessages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus platformchangemessages get <id> --agent` | Get single platformchangemessage |
| `nexudus platformchangemessages create --title <value> --agent` | Create platformchangemessage |
| `nexudus platformchangemessages update <id> --name "New Name" --agent` | Update platformchangemessage |
| `nexudus platformchangemessages delete <id> --yes --agent` | Delete platformchangemessage (no prompt) |

#### PlatformChangeMessage list filter options

`--title`, `--description-english`, `--description-spanish`

#### PlatformChangeMessage create options

`--title` (required), `--description-english`, `--description-spanish`

#### PlatformChangeMessage update options

`--title`, `--description-english`, `--description-spanish`

<!-- END:GENERATED entity=PlatformChangeMessages -->
