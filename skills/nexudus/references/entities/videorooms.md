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

`--business-id`, `--name`, `--description`, `--new-image-url`, `--clear-image-file`, `--number-of-participants`, `--from-number-of-participants` (range), `--to-number-of-participants` (range), `--active`, `--only-for-contacts`, `--only-for-members`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### VideoRoom create options

`--business-id` (required), `--name` (required), `--description`, `--new-image-url`, `--clear-image-file`, `--number-of-participants` (required), `--active`, `--only-for-contacts`, `--only-for-members`

#### VideoRoom update options

`--business-id`, `--name`, `--description`, `--new-image-url`, `--clear-image-file`, `--number-of-participants`, `--active`, `--only-for-contacts`, `--only-for-members`

<!-- END:GENERATED entity=VideoRooms -->
