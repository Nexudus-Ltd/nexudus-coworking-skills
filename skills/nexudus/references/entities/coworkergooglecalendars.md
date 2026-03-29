# CoworkerGoogleCalendars

<!-- BEGIN:GENERATED entity=CoworkerGoogleCalendars -->

CoworkerGoogleCalendars support Search, Get, Create, Update, Delete.
CoworkerGoogleCalendars also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkergooglecalendars list --agent` | List all coworkergooglecalendars |
| `nexudus coworkergooglecalendars list --query "search" --agent` | Search coworkergooglecalendars by name |
| `nexudus coworkergooglecalendars list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkergooglecalendars get <id> --agent` | Get single coworkergooglecalendar |
| `nexudus coworkergooglecalendars create --resource-id <value> --coworker-id <value> --name <value> --agent` | Create coworkergooglecalendar |
| `nexudus coworkergooglecalendars update <id> --name "New Name" --agent` | Update coworkergooglecalendar |
| `nexudus coworkergooglecalendars delete <id> --yes --agent` | Delete coworkergooglecalendar (no prompt) |
| `nexudus coworkergooglecalendars run-command <key> <ids> --agent` | Run entity command |

#### CoworkerGoogleCalendar create options

`--resource-id` (required), `--coworker-id` (required), `--name` (required), `--subscription-id`, `--calendar-id`, `--subscription-expire-date`, `--watch-resource-id`, `--event-sync-token`

#### CoworkerGoogleCalendar update options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`, `--watch-resource-id`, `--event-sync-token`

### CoworkerGoogleCalendar (key fields)

`Id`, `ResourceId`, `CoworkerId`, `CoworkerFullName`, `Name`, `SubscriptionExpireDate`

<!-- END:GENERATED entity=CoworkerGoogleCalendars -->
