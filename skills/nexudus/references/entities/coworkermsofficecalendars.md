# CoworkerMsOfficeCalendars

<!-- BEGIN:GENERATED entity=CoworkerMsOfficeCalendars -->

CoworkerMsOfficeCalendars support Search, Get, Create, Update, Delete.
CoworkerMsOfficeCalendars also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkermsofficecalendars list --agent` | List all coworkermsofficecalendars |
| `nexudus coworkermsofficecalendars list --query "search" --agent` | Search coworkermsofficecalendars by name |
| `nexudus coworkermsofficecalendars list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkermsofficecalendars get <id> --agent` | Get single coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars create --resource-id <value> --coworker-id <value> --name <value> --subscription-expire-date <value> --agent` | Create coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars update <id> --name "New Name" --agent` | Update coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars delete <id> --yes --agent` | Delete coworkermsofficecalendar (no prompt) |
| `nexudus coworkermsofficecalendars run-command <key> <ids> --agent` | Run entity command |

#### CoworkerMsOfficeCalendar create options

`--resource-id` (required), `--coworker-id` (required), `--name` (required), `--subscription-id`, `--calendar-id`, `--subscription-expire-date` (required)

#### CoworkerMsOfficeCalendar update options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`

### CoworkerMsOfficeCalendar (key fields)

`Id`, `ResourceId`, `CoworkerId`, `CoworkerFullName`, `Name`

<!-- END:GENERATED entity=CoworkerMsOfficeCalendars -->
