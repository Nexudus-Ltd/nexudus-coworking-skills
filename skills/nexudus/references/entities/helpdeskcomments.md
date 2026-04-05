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

`--help-desk-message-id`, `--coworker-id`, `--message-text`, `--internal`, `--new-image-url`, `--clear-image-file`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### HelpDeskComment create options

`--help-desk-message-id` (required), `--coworker-id` (required), `--message-text` (required), `--internal`, `--new-image-url`, `--clear-image-file`

#### HelpDeskComment update options

`--help-desk-message-id`, `--coworker-id`, `--message-text`, `--internal`, `--new-image-url`, `--clear-image-file`

<!-- END:GENERATED entity=HelpDeskComments -->
