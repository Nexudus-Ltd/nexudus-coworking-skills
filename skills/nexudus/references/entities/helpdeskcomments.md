# HelpDeskComments

<!-- BEGIN:GENERATED entity=HelpDeskComments -->

A **HelpDeskComment** represents a reply or internal note on a help desk message (support ticket). Comments track the conversation between staff and customers on a support request.

HelpDeskComments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus helpdeskcomments list --agent` | List all helpdeskcomments |
| `nexudus helpdeskcomments list --id <id> --agent` | Filter by single ID |
| `nexudus helpdeskcomments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus helpdeskcomments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus helpdeskcomments list --help-desk-message-id <value> --coworker-id <value> --agent` | Filter helpdeskcomments by properties |
| `nexudus helpdeskcomments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus helpdeskcomments list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus helpdeskcomments get <id> --agent` | Get single helpdeskcomment |
| `nexudus helpdeskcomments create --help-desk-message-id <value> --coworker-id <value> --message-text <value> --agent` | Create helpdeskcomment |
| `nexudus helpdeskcomments update <id> --name "New Name" --agent` | Update helpdeskcomment |
| `nexudus helpdeskcomments delete <id> --yes --agent` | Delete helpdeskcomment (no prompt) |

#### HelpDeskComment list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--help-desk-message-id` | long | ID of the help desk message linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--message-text` | string | The message text value for this help desk comment |
| `--internal` | bool | Whether internal is enabled |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### HelpDeskComment sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### HelpDeskComment create options

| Option | Type | Description |
| --- | --- | --- |
| `--help-desk-message-id` | long, required | ID of the help desk message linked to this record |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--message-text` | string, required | The message text value for this help desk comment |
| `--internal` | bool | Whether internal is enabled |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |

#### HelpDeskComment update options

| Option | Type | Description |
| --- | --- | --- |
| `--help-desk-message-id` | long | ID of the help desk message linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--message-text` | string | The message text value for this help desk comment |
| `--internal` | bool | Whether internal is enabled |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |

#### HelpDeskComment PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus helpdeskcomments update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=HelpDeskComments -->
