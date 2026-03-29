# MsOfficeAdminCalendars

<!-- BEGIN:GENERATED entity=MsOfficeAdminCalendars -->

MsOfficeAdminCalendars support Search, Get, Create, Update, Delete.
MsOfficeAdminCalendars also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus msofficeadmincalendars list --agent` | List all msofficeadmincalendars |
| `nexudus msofficeadmincalendars list --query "search" --agent` | Search msofficeadmincalendars by name |
| `nexudus msofficeadmincalendars list --page 2 --size 10 --agent` | Paginated list |
| `nexudus msofficeadmincalendars get <id> --agent` | Get single msofficeadmincalendar |
| `nexudus msofficeadmincalendars create --resource-id <value> --business <value> --name <value> --subscription-expire-date <value> --agent` | Create msofficeadmincalendar |
| `nexudus msofficeadmincalendars update <id> --name "New Name" --agent` | Update msofficeadmincalendar |
| `nexudus msofficeadmincalendars delete <id> --yes --agent` | Delete msofficeadmincalendar (no prompt) |
| `nexudus msofficeadmincalendars run-command <key> <ids> --agent` | Run entity command |

#### MsOfficeAdminCalendar create options

`--resource-id` (required), `--business` (required), `--name` (required), `--subscription-id`, `--calendar-id`, `--subscription-expire-date` (required)

#### MsOfficeAdminCalendar update options

`--resource-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`

### MsOfficeAdminCalendar (key fields)

`Id`, `ResourceId`, `BusinessId`, `Name`

<!-- END:GENERATED entity=MsOfficeAdminCalendars -->
