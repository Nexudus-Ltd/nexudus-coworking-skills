# CalendarEventCategories

<!-- BEGIN:GENERATED entity=CalendarEventCategories -->

CalendarEventCategories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus calendareventcategories list --agent` | List all calendareventcategories |
| `nexudus calendareventcategories list --id <id> --agent` | Filter by single ID |
| `nexudus calendareventcategories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus calendareventcategories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus calendareventcategories list --business-id <value> --title <value> --agent` | Filter calendareventcategories by properties |
| `nexudus calendareventcategories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus calendareventcategories get <id> --agent` | Get single calendareventcategory |
| `nexudus calendareventcategories create --business-id <value> --title <value> --agent` | Create calendareventcategory |
| `nexudus calendareventcategories update <id> --name "New Name" --agent` | Update calendareventcategory |
| `nexudus calendareventcategories delete <id> --yes --agent` | Delete calendareventcategory (no prompt) |

#### CalendarEventCategory list filter options

`--business-id`, `--title`

#### CalendarEventCategory create options

`--business-id` (required), `--title` (required), `--calendar-events` (list, repeat flag), `--added-calendar-events` (list, repeat flag), `--removed-calendar-events` (list, repeat flag)

#### CalendarEventCategory update options

`--business-id`, `--title`, `--calendar-events` (list, repeat flag), `--added-calendar-events` (list, repeat flag), `--removed-calendar-events` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `CalendarEvents`, `AddedCalendarEvents`, `RemovedCalendarEvents`

<!-- END:GENERATED entity=CalendarEventCategories -->
