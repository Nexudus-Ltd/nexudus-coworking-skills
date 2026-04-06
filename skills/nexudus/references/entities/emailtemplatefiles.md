# EmailTemplateFiles

<!-- BEGIN:GENERATED entity=EmailTemplateFiles -->

EmailTemplateFiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus emailtemplatefiles list --agent` | List all emailtemplatefiles |
| `nexudus emailtemplatefiles list --id <id> --agent` | Filter by single ID |
| `nexudus emailtemplatefiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus emailtemplatefiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus emailtemplatefiles list --business-id <value> --language <value> --agent` | Filter emailtemplatefiles by properties |
| `nexudus emailtemplatefiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus emailtemplatefiles get <id> --agent` | Get single emailtemplatefile |
| `nexudus emailtemplatefiles create --business-id <value> --language <value> --name <value> --subject <value> --agent` | Create emailtemplatefile |
| `nexudus emailtemplatefiles update <id> --name "New Name" --agent` | Update emailtemplatefile |
| `nexudus emailtemplatefiles delete <id> --yes --agent` | Delete emailtemplatefile (no prompt) |

#### EmailTemplateFile list filter options

`--business-id`, `--language`, `--file-language-id`, `--name`, `--subject`, `--file-contents`, `--is-text-only`, `--from-name`, `--from-email`, `--c-c-email`, `--c-c-o-email`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EmailTemplateFile create options

`--business-id` (required), `--language` (required), `--file-language-id`, `--name` (required), `--subject` (required), `--file-contents`, `--is-text-only`, `--from-name`, `--from-email`, `--c-c-email`, `--c-c-o-email`

#### EmailTemplateFile update options

`--business-id`, `--language`, `--file-language-id`, `--name`, `--subject`, `--file-contents`, `--is-text-only`, `--from-name`, `--from-email`, `--c-c-email`, `--c-c-o-email`

<!-- END:GENERATED entity=EmailTemplateFiles -->
