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
| `nexudus coworkergooglecalendars list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkergooglecalendars get <id> --agent` | Get single coworkergooglecalendar |
| `nexudus coworkergooglecalendars create --resource-id <value> --name <value> --subscription-id <value> --calendar-id <value> --subscription-expire-date <value> --watch-resource-id <value> --agent` | Create coworkergooglecalendar |
| `nexudus coworkergooglecalendars update <id> --name "New Name" --agent` | Update coworkergooglecalendar |
| `nexudus coworkergooglecalendars delete <id> --yes --agent` | Delete coworkergooglecalendar (no prompt) |

#### CoworkerGoogleCalendar list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the Nexudus resource (room or desk) used as the Google Calendar push-notification watch target for this connection |
| `--coworker-id` | long | ID of the customer who connected their Google Calendar |
| `--name` | string | Display name of the connected Google Calendar |
| `--subscription-id` | string | Google push-notification channel ID used to receive calendar change notifications |
| `--calendar-id` | string | Google Calendar ID of the customer's connected calendar (e.g. user@gmail.com or a secondary calendar ID) |
| `--subscription-expire-date` | DateTime | Date and time when the Google push-notification channel subscription expires and must be renewed |
| `--from-subscription-expire-date` | range | |
| `--to-subscription-expire-date` | range | |
| `--watch-resource-id` | string | Google-assigned resource ID for the active push-notification watch channel |
| `--event-sync-token` | string | Incremental sync token returned by the Google Calendar API, used to fetch only events changed since the last sync |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerGoogleCalendar sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerGoogleCalendar create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the Nexudus resource (room or desk) used as the Google Calendar push-notification watch target for this connection |
| `--coworker-id` | long | ID of the customer who connected their Google Calendar |
| `--name` | string, required | Display name of the connected Google Calendar |
| `--subscription-id` | string, required | Google push-notification channel ID used to receive calendar change notifications |
| `--calendar-id` | string, required | Google Calendar ID of the customer's connected calendar (e.g. user@gmail.com or a secondary calendar ID) |
| `--subscription-expire-date` | DateTime, required | Date and time when the Google push-notification channel subscription expires and must be renewed |
| `--watch-resource-id` | string, required | Google-assigned resource ID for the active push-notification watch channel |
| `--event-sync-token` | string | Incremental sync token returned by the Google Calendar API, used to fetch only events changed since the last sync |

#### CoworkerGoogleCalendar update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the Nexudus resource (room or desk) used as the Google Calendar push-notification watch target for this connection |
| `--coworker-id` | long | ID of the customer who connected their Google Calendar |
| `--name` | string | Display name of the connected Google Calendar |
| `--subscription-id` | string | Google push-notification channel ID used to receive calendar change notifications |
| `--calendar-id` | string | Google Calendar ID of the customer's connected calendar (e.g. user@gmail.com or a secondary calendar ID) |
| `--subscription-expire-date` | DateTime | Date and time when the Google push-notification channel subscription expires and must be renewed |
| `--watch-resource-id` | string | Google-assigned resource ID for the active push-notification watch channel |
| `--event-sync-token` | string | Incremental sync token returned by the Google Calendar API, used to fetch only events changed since the last sync |

#### CoworkerGoogleCalendar PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkergooglecalendars update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerGoogleCalendar (key fields)

`Id`, `CoworkerFullName`, `Name`

<!-- END:GENERATED entity=CoworkerGoogleCalendars -->
