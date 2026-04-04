# TemplateFiles

<!-- BEGIN:GENERATED entity=TemplateFiles -->

TemplateFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus templatefiles list --agent` | List all templatefiles |
| `nexudus templatefiles list --id <id> --agent` | Filter by single ID |
| `nexudus templatefiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus templatefiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus templatefiles list --business-id <value> --template-version-id <value> --agent` | Filter templatefiles by properties |
| `nexudus templatefiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus templatefiles get <id> --agent` | Get single templatefile |
| `nexudus templatefiles create --business-id <value> --name <value> --permalink <value> --agent` | Create templatefile |
| `nexudus templatefiles update <id> --name "New Name" --agent` | Update templatefile |
| `nexudus templatefiles delete <id> --yes --agent` | Delete templatefile (no prompt) |

#### TemplateFile list filter options

`--business-id`, `--template-version-id`, `--name`, `--title`, `--description`, `--new-picture-url`, `--clear-picture`, `--permalink`, `--file-language-id`, `--published`, `--visibility`, `--password`, `--file-contents`

#### TemplateFile create options

`--business-id` (required), `--template-version-id`, `--name` (required), `--title`, `--description`, `--new-picture-url`, `--clear-picture`, `--permalink` (required), `--file-language-id`, `--published`, `--visibility`, `--password`, `--file-contents`

#### TemplateFile update options

`--business-id`, `--template-version-id`, `--name`, `--title`, `--description`, `--new-picture-url`, `--clear-picture`, `--permalink`, `--file-language-id`, `--published`, `--visibility`, `--password`, `--file-contents`

<!-- END:GENERATED entity=TemplateFiles -->
