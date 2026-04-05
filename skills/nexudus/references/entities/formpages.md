# FormPages

<!-- BEGIN:GENERATED entity=FormPages -->

FormPages support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus formpages list --agent` | List all formpages |
| `nexudus formpages list --id <id> --agent` | Filter by single ID |
| `nexudus formpages list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus formpages list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus formpages list --business-id <value> --name <value> --agent` | Filter formpages by properties |
| `nexudus formpages list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus formpages get <id> --agent` | Get single formpage |
| `nexudus formpages create --business-id <value> --name <value> --description <value> --agent` | Create formpage |
| `nexudus formpages update <id> --name "New Name" --agent` | Update formpage |
| `nexudus formpages delete <id> --yes --agent` | Delete formpage (no prompt) |

#### FormPage list filter options

`--business-id`, `--name`, `--description`, `--active`, `--crm-board-column-id`, `--responsible-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FormPage create options

`--business-id` (required), `--name` (required), `--description` (required), `--active`, `--crm-board-column-id`, `--responsible-id`

#### FormPage update options

`--business-id`, `--name`, `--description`, `--active`, `--crm-board-column-id`, `--responsible-id`

<!-- END:GENERATED entity=FormPages -->
