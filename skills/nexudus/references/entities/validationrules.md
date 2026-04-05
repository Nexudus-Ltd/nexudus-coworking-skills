# ValidationRules

<!-- BEGIN:GENERATED entity=ValidationRules -->

ValidationRules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus validationrules list --agent` | List all validationrules |
| `nexudus validationrules list --id <id> --agent` | Filter by single ID |
| `nexudus validationrules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus validationrules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus validationrules list --business-id <value> --name <value> --agent` | Filter validationrules by properties |
| `nexudus validationrules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus validationrules get <id> --agent` | Get single validationrule |
| `nexudus validationrules create --business-id <value> --name <value> --formula <value> --agent` | Create validationrule |
| `nexudus validationrules update <id> --name "New Name" --agent` | Update validationrule |
| `nexudus validationrules delete <id> --yes --agent` | Delete validationrule (no prompt) |

#### ValidationRule list filter options

`--business-id`, `--name`, `--record-type`, `--active`, `--formula`, `--description`, `--error-message`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ValidationRule create options

`--business-id` (required), `--name` (required), `--record-type`, `--active`, `--formula` (required), `--description`, `--error-message`

#### ValidationRule update options

`--business-id`, `--name`, `--record-type`, `--active`, `--formula`, `--description`, `--error-message`

<!-- END:GENERATED entity=ValidationRules -->
