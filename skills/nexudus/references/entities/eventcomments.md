# EventComments

<!-- BEGIN:GENERATED entity=EventComments -->

EventComments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventcomments list --agent` | List all eventcomments |
| `nexudus eventcomments list --id <id> --agent` | Filter by single ID |
| `nexudus eventcomments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventcomments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventcomments list --business-id <value> --calendar-event-id <value> --agent` | Filter eventcomments by properties |
| `nexudus eventcomments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventcomments get <id> --agent` | Get single eventcomment |
| `nexudus eventcomments create --business-id <value> --calendar-event-id <value> --title <value> --text <value> --agent` | Create eventcomment |
| `nexudus eventcomments update <id> --name "New Name" --agent` | Update eventcomment |
| `nexudus eventcomments delete <id> --yes --agent` | Delete eventcomment (no prompt) |

#### EventComment list filter options

`--business-id`, `--calendar-event-id`, `--posted-by-id`, `--title`, `--text`, `--published`, `--rating`, `--from-rating` (range), `--to-rating` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### EventComment create options

`--business-id` (required), `--calendar-event-id` (required), `--posted-by-id`, `--title` (required), `--text` (required), `--published`, `--rating`

#### EventComment update options

`--business-id`, `--calendar-event-id`, `--posted-by-id`, `--title`, `--text`, `--published`, `--rating`

<!-- END:GENERATED entity=EventComments -->
