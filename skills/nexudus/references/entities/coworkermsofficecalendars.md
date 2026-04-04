# CoworkerMsOfficeCalendars

<!-- BEGIN:GENERATED entity=CoworkerMsOfficeCalendars -->

CoworkerMsOfficeCalendars support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkermsofficecalendars list --agent` | List all coworkermsofficecalendars |
| `nexudus coworkermsofficecalendars list --id <id> --agent` | Filter by single ID |
| `nexudus coworkermsofficecalendars list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkermsofficecalendars list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkermsofficecalendars list --resource-id <value> --coworker-id <value> --agent` | Filter coworkermsofficecalendars by properties |
| `nexudus coworkermsofficecalendars list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkermsofficecalendars get <id> --agent` | Get single coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars create --resource-id <value> --name <value> --subscription-id <value> --calendar-id <value> --subscription-expire-date <value> --agent` | Create coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars update <id> --name "New Name" --agent` | Update coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars delete <id> --yes --agent` | Delete coworkermsofficecalendar (no prompt) |

#### CoworkerMsOfficeCalendar list filter options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`

#### CoworkerMsOfficeCalendar create options

`--resource-id` (required), `--coworker-id`, `--name` (required), `--subscription-id` (required), `--calendar-id` (required), `--subscription-expire-date` (required)

#### CoworkerMsOfficeCalendar update options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`

<!-- END:GENERATED entity=CoworkerMsOfficeCalendars -->
