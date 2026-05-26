# HelpDeskComments

<!-- BEGIN:GENERATED entity=HelpDeskComments -->

HelpDeskComments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus helpdeskcomments list --agent` | List all helpdeskcomments |
| `nexudus helpdeskcomments list --id <id> --agent` | Filter by single ID |
| `nexudus helpdeskcomments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus helpdeskcomments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus helpdeskcomments list --help-desk-message-id <value> --coworker-id <value> --agent` | Filter helpdeskcomments by properties |
| `nexudus helpdeskcomments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus helpdeskcomments get <id> --agent` | Get single helpdeskcomment |
| `nexudus helpdeskcomments create --help-desk-message-id <value> --coworker-id <value> --message-text <value> --agent` | Create helpdeskcomment |
| `nexudus helpdeskcomments update <id> --name "New Name" --agent` | Update helpdeskcomment |
| `nexudus helpdeskcomments delete <id> --yes --agent` | Delete helpdeskcomment (no prompt) |

#### HelpDeskComment list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--help-desk-message-id` | long |  |
| `--coworker-id` | long |  |
| `--message-text` | string |  |
| `--internal` | bool |  |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### HelpDeskComment create options

| Option | Type | Description |
| --- | --- | --- |
| `--help-desk-message-id` | long, required |  |
| `--coworker-id` | long, required |  |
| `--message-text` | string, required |  |
| `--internal` | bool |  |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |

#### HelpDeskComment update options

| Option | Type | Description |
| --- | --- | --- |
| `--help-desk-message-id` | long |  |
| `--coworker-id` | long |  |
| `--message-text` | string |  |
| `--internal` | bool |  |
| `--new-image-url` | string |  |
| `--clear-image-file` | bool |  |

#### HelpDeskComment PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus helpdeskcomments update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=HelpDeskComments -->
