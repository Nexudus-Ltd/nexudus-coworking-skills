# MsOfficeAdminCalendars

<!-- BEGIN:GENERATED entity=MsOfficeAdminCalendars -->

An **MsOfficeAdminCalendar** configures a Microsoft Office 365 calendar integration for administrators, enabling two-way synchronisation of bookings and events between Nexudus and Outlook.

MsOfficeAdminCalendars support Search, Get, Create, Update, Delete.
MsOfficeAdminCalendars also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus msofficeadmincalendars list --agent` | List all msofficeadmincalendars |
| `nexudus msofficeadmincalendars list --id <id> --agent` | Filter by single ID |
| `nexudus msofficeadmincalendars list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus msofficeadmincalendars list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus msofficeadmincalendars list --name <value> --agent` | Filter msofficeadmincalendars by properties |
| `nexudus msofficeadmincalendars list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus msofficeadmincalendars list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus msofficeadmincalendars get <id> --agent` | Get single msofficeadmincalendar |
| `nexudus msofficeadmincalendars create --resource-id <value> --business-id <value> --name <value> --subscription-id <value> --calendar-id <value> --subscription-expire-date <value> --agent` | Create msofficeadmincalendar |
| `nexudus msofficeadmincalendars update <id> --name "New Name" --agent` | Update msofficeadmincalendar |
| `nexudus msofficeadmincalendars delete <id> --yes --agent` | Delete msofficeadmincalendar (no prompt) |
| `nexudus msofficeadmincalendars run-command <key> <ids> --agent` | Run entity command |

#### MsOfficeAdminCalendar list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Calendar name |
| `--subscription-id` | string | Subscription ID |
| `--calendar-id` | string | Calendar ID |
| `--subscription-expire-date` | DateTime | Subscription expiration date |
| `--from-subscription-expire-date` | range | |
| `--to-subscription-expire-date` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### MsOfficeAdminCalendar sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### MsOfficeAdminCalendar create options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long, required | ID of the resource linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Calendar name |
| `--subscription-id` | string, required | Subscription ID |
| `--calendar-id` | string, required | Calendar ID |
| `--subscription-expire-date` | DateTime, required | Subscription expiration date |

#### MsOfficeAdminCalendar update options

| Option | Type | Description |
| --- | --- | --- |
| `--resource-id` | long | ID of the resource linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Calendar name |
| `--subscription-id` | string | Subscription ID |
| `--calendar-id` | string | Calendar ID |
| `--subscription-expire-date` | DateTime | Subscription expiration date |

### MsOfficeAdminCalendar (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=MsOfficeAdminCalendars -->
