# CoworkerMsOfficeCalendars

<!-- BEGIN:GENERATED entity=CoworkerMsOfficeCalendars -->

A **CoworkerMsOfficeCalendar** record represents a Microsoft Office 365 Calendar account connected to a customer's Nexudus account.

These records are created automatically when a customer connects their Office 365 Calendar from the Members Portal or the Nexudus app. Once connected, customers can book resources at a location directly from their Office 365 Calendar.

Each record stores the Microsoft Graph push-notification subscription details (`SubscriptionId`, `SubscriptionExpireDate`) used to keep the calendar in sync.

For more information, see the [Office 365 Calendar (Customer)](https://help.nexudus.com/docs/office-365-calendar-customer) help article.

CoworkerMsOfficeCalendars support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkermsofficecalendars list --agent` | List all coworkermsofficecalendars |
| `nexudus coworkermsofficecalendars list --id <id> --agent` | Filter by single ID |
| `nexudus coworkermsofficecalendars list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkermsofficecalendars list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkermsofficecalendars list --name <value> --agent` | Filter coworkermsofficecalendars by properties |
| `nexudus coworkermsofficecalendars list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkermsofficecalendars get <id> --agent` | Get single coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars create --resource-id <value> --name <value> --subscription-id <value> --calendar-id <value> --subscription-expire-date <value> --agent` | Create coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars update <id> --name "New Name" --agent` | Update coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars delete <id> --yes --agent` | Delete coworkermsofficecalendar (no prompt) |

#### CoworkerMsOfficeCalendar list filter options

`--resource-id` (long), `--coworker-id` (long), `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date` (DateTime), `--from-subscription-expire-date` (range), `--to-subscription-expire-date` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerMsOfficeCalendar create options

`--resource-id` (long, required), `--coworker-id` (long), `--name` (required), `--subscription-id` (required), `--calendar-id` (required), `--subscription-expire-date` (DateTime, required)

#### CoworkerMsOfficeCalendar update options

`--resource-id` (long), `--coworker-id` (long), `--name`, `--subscription-id`, `--calendar-id`, `--subscription-expire-date` (DateTime)

### CoworkerMsOfficeCalendar (key fields)

`Id`, `CoworkerFullName`, `Name`

<!-- END:GENERATED entity=CoworkerMsOfficeCalendars -->
