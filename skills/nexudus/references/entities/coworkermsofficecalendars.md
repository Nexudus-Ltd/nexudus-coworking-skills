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
| `nexudus coworkermsofficecalendars list --coworker-full-name <value> --name <value> --agent` | Filter coworkermsofficecalendars by properties |
| `nexudus coworkermsofficecalendars list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkermsofficecalendars list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkermsofficecalendars get <id> --agent` | Get single coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars create --resource-id <value> --name <value> --subscription-id <value> --calendar-id <value> --subscription-expire-date <value> --agent` | Create coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars update <id> --name "New Name" --agent` | Update coworkermsofficecalendar |
| `nexudus coworkermsofficecalendars delete <id> --yes --agent` | Delete coworkermsofficecalendar (no prompt) |

#### CoworkerMsOfficeCalendar list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the Nexudus resource (room or desk) used as the Microsoft Graph push-notification watch target for this connection |
| `--coworker-id` | long | ID of the customer who connected their Office 365 Calendar |
| `--coworker-full-name` | string | Full name of the customer who connected their Office 365 Calendar |
| `--name` | string | Display name of the connected Office 365 Calendar |
| `--subscription-id` | string | Microsoft Graph push-notification subscription ID used to receive calendar change notifications |
| `--calendar-id` | string | Microsoft Graph calendar ID of the customer's connected Office 365 calendar |
| `--subscription-expire-date` | DateTime | Date and time when the Microsoft Graph push-notification subscription expires and must be renewed |
| `--from-subscription-expire-date` | range | |
| `--to-subscription-expire-date` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerMsOfficeCalendar sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerMsOfficeCalendar create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the Nexudus resource (room or desk) used as the Microsoft Graph push-notification watch target for this connection |
| `--coworker-id` | long | ID of the customer who connected their Office 365 Calendar |
| `--name` | string, required | Display name of the connected Office 365 Calendar |
| `--subscription-id` | string, required | Microsoft Graph push-notification subscription ID used to receive calendar change notifications |
| `--calendar-id` | string, required | Microsoft Graph calendar ID of the customer's connected Office 365 calendar |
| `--subscription-expire-date` | DateTime, required | Date and time when the Microsoft Graph push-notification subscription expires and must be renewed |

#### CoworkerMsOfficeCalendar update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the Nexudus resource (room or desk) used as the Microsoft Graph push-notification watch target for this connection |
| `--coworker-id` | long | ID of the customer who connected their Office 365 Calendar |
| `--name` | string | Display name of the connected Office 365 Calendar |
| `--subscription-id` | string | Microsoft Graph push-notification subscription ID used to receive calendar change notifications |
| `--calendar-id` | string | Microsoft Graph calendar ID of the customer's connected Office 365 calendar |
| `--subscription-expire-date` | DateTime | Date and time when the Microsoft Graph push-notification subscription expires and must be renewed |

#### CoworkerMsOfficeCalendar PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkermsofficecalendars update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerMsOfficeCalendar (key fields)

`Id`, `CoworkerFullName`, `Name`

<!-- END:GENERATED entity=CoworkerMsOfficeCalendars -->
