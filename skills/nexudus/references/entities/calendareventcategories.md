# CalendarEventCategories

<!-- BEGIN:GENERATED entity=CalendarEventCategories -->

A **CalendarEventCategory** groups events by type or theme within a location. Categories appear as filters on the Events page of the Members Portal, letting customers quickly find relevant events. Events that share the same category are also shown as related events when a customer views the detail page of a specific event.

Assign categories to events via the `EventCategories` list on the `CalendarEvent` entity.

CalendarEventCategories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus calendareventcategories list --agent` | List all calendareventcategories |
| `nexudus calendareventcategories list --id <id> --agent` | Filter by single ID |
| `nexudus calendareventcategories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus calendareventcategories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus calendareventcategories list --title <value> --agent` | Filter calendareventcategories by properties |
| `nexudus calendareventcategories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus calendareventcategories get <id> --agent` | Get single calendareventcategory |
| `nexudus calendareventcategories create --business-id <value> --title <value> --agent` | Create calendareventcategory |
| `nexudus calendareventcategories update <id> --name "New Name" --agent` | Update calendareventcategory |
| `nexudus calendareventcategories delete <id> --yes --agent` | Delete calendareventcategory (no prompt) |

#### CalendarEventCategory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | The location this event category belongs to |
| `--title` | string | Category name shown as a filter on the Members Portal |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CalendarEventCategory create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | The location this event category belongs to |
| `--title` | string, required | Category name shown as a filter on the Members Portal |
| `--calendar-events` | list, repeat flag | IDs of events assigned to this category |
| `--added-calendar-events` | list, repeat flag |  |
| `--removed-calendar-events` | list, repeat flag |  |

#### CalendarEventCategory update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | The location this event category belongs to |
| `--title` | string | Category name shown as a filter on the Members Portal |
| `--calendar-events` | list, repeat flag | IDs of events assigned to this category |
| `--added-calendar-events` | list, repeat flag |  |
| `--removed-calendar-events` | list, repeat flag |  |

### CalendarEventCategory (key fields)

`Id`, `Title`

**List properties (only returned by `get`, not by `list`):** `CalendarEvents`, `AddedCalendarEvents`, `RemovedCalendarEvents`

<!-- END:GENERATED entity=CalendarEventCategories -->
