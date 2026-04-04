# DocumentTemplates

<!-- BEGIN:GENERATED entity=DocumentTemplates -->

DocumentTemplates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus documenttemplates list --agent` | List all documenttemplates |
| `nexudus documenttemplates list --id <id> --agent` | Filter by single ID |
| `nexudus documenttemplates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus documenttemplates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus documenttemplates list --business-id <value> --name <value> --agent` | Filter documenttemplates by properties |
| `nexudus documenttemplates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus documenttemplates get <id> --agent` | Get single documenttemplate |
| `nexudus documenttemplates create --business-id <value> --name <value> --agent` | Create documenttemplate |
| `nexudus documenttemplates update <id> --name "New Name" --agent` | Update documenttemplate |
| `nexudus documenttemplates delete <id> --yes --agent` | Delete documenttemplate (no prompt) |

#### DocumentTemplate list filter options

`--business-id`, `--name`, `--document`, `--new-binary-document-url`, `--clear-binary-document`, `--template-output-format`

#### DocumentTemplate create options

`--business-id` (required), `--name` (required), `--document`, `--new-binary-document-url`, `--clear-binary-document`, `--template-output-format`

#### DocumentTemplate update options

`--business-id`, `--name`, `--document`, `--new-binary-document-url`, `--clear-binary-document`, `--template-output-format`

<!-- END:GENERATED entity=DocumentTemplates -->
