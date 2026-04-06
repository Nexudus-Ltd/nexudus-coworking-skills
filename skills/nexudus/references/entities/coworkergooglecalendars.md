# CoworkerGoogleCalendars

<!-- BEGIN:GENERATED entity=CoworkerGoogleCalendars -->

A **CoworkerGoogleCalendar** record represents a Google Calendar account connected to a customer's Nexudus account.

These records are created automatically when a customer connects their own Google Calendar from the Members Portal or the Nexudus app. Once connected, customers can book resources at a location directly from their Google Calendar.

Each record stores the Google push-notification subscription details (`SubscriptionId`, `WatchResourceId`, `SubscriptionExpireDate`) used to keep the calendar in sync, as well as an `EventSyncToken` for incremental Google Calendar API event queries.

For more information, see the [Google Calendar (Customer)](https://help.nexudus.com/docs/google-calendar-customer) help article.

CoworkerGoogleCalendars support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkergooglecalendars list --agent` | List all coworkergooglecalendars |
| `nexudus coworkergooglecalendars list --id <id> --agent` | Filter by single ID |
| `nexudus coworkergooglecalendars list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkergooglecalendars list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkergooglecalendars list --name <value> --agent` | Filter coworkergooglecalendars by properties |
| `nexudus coworkergooglecalendars list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkergooglecalendars get <id> --agent` | Get single coworkergooglecalendar |
| `nexudus coworkergooglecalendars create --resource-id <value> --name <value> --subscription-id <value> --calendar-id <value> --subscription-expire-date <value> --watch-resource-id <value> --agent` | Create coworkergooglecalendar |
| `nexudus coworkergooglecalendars update <id> --name "New Name" --agent` | Update coworkergooglecalendar |
| `nexudus coworkergooglecalendars delete <id> --yes --agent` | Delete coworkergooglecalendar (no prompt) |

#### CoworkerGoogleCalendar list filter options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`, `--from-subscription-expire-date` (range), `--to-subscription-expire-date` (range), `--watch-resource-id`, `--event-sync-token`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerGoogleCalendar create options

`--resource-id` (required), `--coworker-id`, `--name` (required), `--subscription-id` (required), `--calendar-id` (required), `--subscription-expire-date` (required), `--watch-resource-id` (required), `--event-sync-token`

#### CoworkerGoogleCalendar update options

`--resource-id`, `--coworker-id`, `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date`, `--watch-resource-id`, `--event-sync-token`

### CoworkerGoogleCalendar (key fields)

`Id`, `CoworkerFullName`, `Name`

<!-- END:GENERATED entity=CoworkerGoogleCalendars -->
