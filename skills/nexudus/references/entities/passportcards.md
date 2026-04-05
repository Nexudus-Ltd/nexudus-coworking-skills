# PassportCards

<!-- BEGIN:GENERATED entity=PassportCards -->

PassportCards support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus passportcards list --agent` | List all passportcards |
| `nexudus passportcards list --id <id> --agent` | Filter by single ID |
| `nexudus passportcards list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus passportcards list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus passportcards list --code <value> --active <value> --agent` | Filter passportcards by properties |
| `nexudus passportcards list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus passportcards get <id> --agent` | Get single passportcard |
| `nexudus passportcards create --code <value> --agent` | Create passportcard |
| `nexudus passportcards update <id> --name "New Name" --agent` | Update passportcard |
| `nexudus passportcards delete <id> --yes --agent` | Delete passportcard (no prompt) |

#### PassportCard list filter options

`--code`, `--active`, `--notes`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### PassportCard create options

`--code` (required), `--active`, `--notes`

#### PassportCard update options

`--code`, `--active`, `--notes`

<!-- END:GENERATED entity=PassportCards -->
