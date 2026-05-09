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

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--calendar-event-id` | long |  |
| `--posted-by-id` | long |  |
| `--title` | string |  |
| `--text` | string |  |
| `--published` | bool |  |
| `--rating` | int |  |
| `--from-rating` | range | |
| `--to-rating` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EventComment create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--calendar-event-id` | long, required |  |
| `--posted-by-id` | long |  |
| `--title` | string, required |  |
| `--text` | string, required |  |
| `--published` | bool |  |
| `--rating` | int |  |

#### EventComment update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--calendar-event-id` | long |  |
| `--posted-by-id` | long |  |
| `--title` | string |  |
| `--text` | string |  |
| `--published` | bool |  |
| `--rating` | int |  |

<!-- END:GENERATED entity=EventComments -->
