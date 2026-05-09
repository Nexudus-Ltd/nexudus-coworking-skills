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
| `nexudus templatefiles create --business-id <value> --name <value> --permalink <value> --visibility <value> --agent` | Create templatefile |
| `nexudus templatefiles update <id> --name "New Name" --agent` | Update templatefile |
| `nexudus templatefiles delete <id> --yes --agent` | Delete templatefile (no prompt) |

#### TemplateFile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--template-version-id` | long |  |
| `--name` | string |  |
| `--title` | string |  |
| `--description` | string |  |
| `--new-picture-url` | string |  |
| `--clear-picture-file` | bool |  |
| `--permalink` | string |  |
| `--file-language-id` | long |  |
| `--published` | bool |  |
| `--visibility` | enum |  |
| `--password` | string |  |
| `--file-contents` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TemplateFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--template-version-id` | long |  |
| `--name` | string, required |  |
| `--title` | string |  |
| `--description` | string |  |
| `--new-picture-url` | string |  |
| `--clear-picture-file` | bool |  |
| `--permalink` | string, required |  |
| `--file-language-id` | long |  |
| `--published` | bool |  |
| `--visibility` | enum, required |  |
| `--password` | string |  |
| `--file-contents` | string |  |

#### TemplateFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--template-version-id` | long |  |
| `--name` | string |  |
| `--title` | string |  |
| `--description` | string |  |
| `--new-picture-url` | string |  |
| `--clear-picture-file` | bool |  |
| `--permalink` | string |  |
| `--file-language-id` | long |  |
| `--published` | bool |  |
| `--visibility` | enum |  |
| `--password` | string |  |
| `--file-contents` | string |  |

<!-- END:GENERATED entity=TemplateFiles -->
