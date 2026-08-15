# HelpDeskComments

<!-- BEGIN:GENERATED entity=HelpDeskComments -->

A HelpDeskComment is a customer or staff reply, including internal notes, on a support ticket; creating one reopens the ticket and follows its notification rules.

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
| `--help-desk-message-id` | long | ID of the support ticket this reply or note belongs to; it determines the owning location and a new comment reopens the ticket. |
| `--coworker-id` | long | ID of the customer or staff member who authored this comment; the author determines the notification path. |
| `--message-text` | string | Required multiline text of the customer reply or staff note. |
| `--internal` | bool | Whether this is an internal staff note; when true it is not sent to the customer. |
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
| `--help-desk-message-id` | long, required | ID of the support ticket this reply or note belongs to; it determines the owning location and a new comment reopens the ticket. |
| `--coworker-id` | long, required | ID of the customer or staff member who authored this comment; the author determines the notification path. |
| `--message-text` | string, required | Required multiline text of the customer reply or staff note. |
| `--internal` | bool | Whether this is an internal staff note; when true it is not sent to the customer. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |

#### HelpDeskComment update options

| Option | Type | Description |
| --- | --- | --- |
| `--help-desk-message-id` | long | ID of the support ticket this reply or note belongs to; it determines the owning location and a new comment reopens the ticket. |
| `--coworker-id` | long | ID of the customer or staff member who authored this comment; the author determines the notification path. |
| `--message-text` | string | Required multiline text of the customer reply or staff note. |
| `--internal` | bool | Whether this is an internal staff note; when true it is not sent to the customer. |
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
