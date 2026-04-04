# CoworkerGoogleCalendars

<!-- BEGIN:GENERATED entity=CoworkerGoogleCalendars -->

CoworkerGoogleCalendars support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkergooglecalendars list --agent` | List all coworkergooglecalendars |
| `nexudus coworkergooglecalendars list --id <id> --agent` | Filter by single ID |
| `nexudus coworkergooglecalendars list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkergooglecalendars list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkergooglecalendars list --resource-id <value> --coworker-id <value> --agent` | Filter coworkergooglecalendars by properties |
| `nexudus coworkergooglecalendars list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkergooglecalendars get <id> --agent` | Get single coworkergooglecalendar |
| `nexudus coworkergooglecalendars create --resource-id <value> --name <value> --subscription-id <value> --calendar-id <value> --subscription-expire-date <value> --watch-resource-id <value> --agent` | Create coworkergooglecalendar |
| `nexudus coworkergooglecalendars update <id> --name "New Name" --agent` | Update coworkergooglecalendar |
| `nexudus coworkergooglecalendars delete <id> --yes --agent` | Delete coworkergooglecalendar (no prompt) |

#### CoworkerGoogleCalendar list filter options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`, `--watch-resource-id`, `--event-sync-token`

#### CoworkerGoogleCalendar create options

`--resource-id` (required), `--coworker-id`, `--name` (required), `--subscription-id` (required), `--calendar-id` (required), `--subscription-expire-date` (required), `--watch-resource-id` (required), `--event-sync-token`

#### CoworkerGoogleCalendar update options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`, `--watch-resource-id`, `--event-sync-token`

<!-- END:GENERATED entity=CoworkerGoogleCalendars -->
