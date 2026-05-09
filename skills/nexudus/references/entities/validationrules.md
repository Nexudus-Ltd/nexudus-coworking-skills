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
| `nexudus validationrules create --business-id <value> --name <value> --record-type <value> --formula <value> --agent` | Create validationrule |
| `nexudus validationrules update <id> --name "New Name" --agent` | Update validationrule |
| `nexudus validationrules delete <id> --yes --agent` | Delete validationrule (no prompt) |

#### ValidationRule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--record-type` | enum |  |
| `--active` | bool |  |
| `--formula` | string |  |
| `--description` | string |  |
| `--error-message` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ValidationRule create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--record-type` | enum, required |  |
| `--active` | bool |  |
| `--formula` | string, required |  |
| `--description` | string |  |
| `--error-message` | string |  |

#### ValidationRule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--record-type` | enum |  |
| `--active` | bool |  |
| `--formula` | string |  |
| `--description` | string |  |
| `--error-message` | string |  |

<!-- END:GENERATED entity=ValidationRules -->
