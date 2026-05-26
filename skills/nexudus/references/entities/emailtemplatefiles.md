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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--language` | enum |  |
| `--file-language-id` | long |  |
| `--name` | string |  |
| `--subject` | string |  |
| `--file-contents` | string |  |
| `--is-text-only` | bool |  |
| `--from-name` | string |  |
| `--from-email` | string |  |
| `--c-c-email` | string |  |
| `--c-c-o-email` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EmailTemplateFile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--language` | enum, required |  |
| `--file-language-id` | long |  |
| `--name` | string, required |  |
| `--subject` | string, required |  |
| `--file-contents` | string |  |
| `--is-text-only` | bool |  |
| `--from-name` | string |  |
| `--from-email` | string |  |
| `--c-c-email` | string |  |
| `--c-c-o-email` | string |  |

#### EmailTemplateFile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--language` | enum |  |
| `--file-language-id` | long |  |
| `--name` | string |  |
| `--subject` | string |  |
| `--file-contents` | string |  |
| `--is-text-only` | bool |  |
| `--from-name` | string |  |
| `--from-email` | string |  |
| `--c-c-email` | string |  |
| `--c-c-o-email` | string |  |

#### EmailTemplateFile PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--from-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--c-c-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--c-c-o-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus emailtemplatefiles update <id> --from-email "«PII:EMAIL:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=EmailTemplateFiles -->
