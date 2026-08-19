# EventComments

<!-- BEGIN:GENERATED entity=EventComments -->

An **EventComment** represents a comment posted by a user on a calendar event. Comments enable discussion and feedback on events within the community.

EventComments support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eventcomments list --agent` | List all eventcomments |
| `nexudus eventcomments list --id <id> --agent` | Filter by single ID |
| `nexudus eventcomments list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eventcomments list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eventcomments list --business-id <value> --calendar-event-id <value> --agent` | Filter eventcomments by properties |
| `nexudus eventcomments list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eventcomments list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus eventcomments get <id> --agent` | Get single eventcomment |
| `nexudus eventcomments create --business-id <value> --calendar-event-id <value> --title <value> --text <value> --agent` | Create eventcomment |
| `nexudus eventcomments update <id> --name "New Name" --agent` | Update eventcomment |
| `nexudus eventcomments delete <id> --yes --agent` | Delete eventcomment (no prompt) |

#### EventComment list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--posted-by-id` | long | ID of the posted by linked to this record |
| `--posted-by-full-name` | string | Display name of the linked posted by full (read-only) |
| `--title` | string | The title value for this event comment |
| `--text` | string | The text value for this event comment |
| `--published` | bool | Whether published is enabled |
| `--rating` | int | The rating value for this event comment |
| `--from-rating` | range | |
| `--to-rating` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### EventComment sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### EventComment create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--calendar-event-id` | long, required | ID of the calendar event linked to this record |
| `--posted-by-id` | long | ID of the posted by linked to this record |
| `--title` | string, required | The title value for this event comment |
| `--text` | string, required | The text value for this event comment |
| `--published` | bool | Whether published is enabled |
| `--rating` | int | The rating value for this event comment |

#### EventComment update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--calendar-event-id` | long | ID of the calendar event linked to this record |
| `--posted-by-id` | long | ID of the posted by linked to this record |
| `--title` | string | The title value for this event comment |
| `--text` | string | The text value for this event comment |
| `--published` | bool | Whether published is enabled |
| `--rating` | int | The rating value for this event comment |

#### EventComment PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--posted-by-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus eventcomments update <id> --posted-by-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=EventComments -->
