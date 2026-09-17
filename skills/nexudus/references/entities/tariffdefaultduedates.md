# TariffDefaultDueDates

<!-- BEGIN:GENERATED entity=TariffDefaultDueDates -->

A plan due date overrides a location's default invoice due date for invoices that include specific plans. Operators manage these under Settings, alongside the location-wide default due date. It is consulted after the customer's own invoice due date settings and before the location default, and when several plan due dates match one invoice the one producing the earliest due date wins.

TariffDefaultDueDates support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus tariffdefaultduedates list --agent` | List all tariffdefaultduedates |
| `nexudus tariffdefaultduedates list --id <id> --agent` | Filter by single ID |
| `nexudus tariffdefaultduedates list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus tariffdefaultduedates list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus tariffdefaultduedates list --auto-collect-on <value> --auto-collect-after <value> --agent` | Filter tariffdefaultduedates by properties |
| `nexudus tariffdefaultduedates list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus tariffdefaultduedates list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus tariffdefaultduedates get <id> --agent` | Get single tariffdefaultduedate |
| `nexudus tariffdefaultduedates create --business-id <value> --agent` | Create tariffdefaultduedate |
| `nexudus tariffdefaultduedates update <id> --name "New Name" --agent` | Update tariffdefaultduedate |
| `nexudus tariffdefaultduedates delete <id> --yes --agent` | Delete tariffdefaultduedate (no prompt) |

#### TariffDefaultDueDate list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this plan due date. A rule also applies to invoices issued by locations further down the same network, because the lookup walks from the invoice location up to its root location. |
| `--auto-collect-on` | int | Day of the FOLLOWING month the invoice becomes due, in the location time zone at the start of that day; -1 means its last day. Takes precedence over AutoCollectAfter, so leave this empty to date the due date from the invoice instead. Keep it at 28 or less so it exists in every month. |
| `--from-auto-collect-on` | range | |
| `--to-auto-collect-on` | range | |
| `--auto-collect-after` | int | Number of days after the invoice date the invoice becomes due; 0 means due immediately. Capped at 365 when the due date is calculated. Used only when AutoCollectOn is empty. |
| `--from-auto-collect-after` | range | |
| `--to-auto-collect-after` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TariffDefaultDueDate sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` descending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (descending).

#### TariffDefaultDueDate create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this plan due date. A rule also applies to invoices issued by locations further down the same network, because the lookup walks from the invoice location up to its root location. |
| `--tariffs` | list, repeat flag | List of plan IDs this due date applies to. An invoice matches when any of its contracts is on one of these plans. An empty list is not a disabled rule: it matches every invoice at the location, acting as a location-wide override of the default due date in Settings. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--auto-collect-on` | int | Day of the FOLLOWING month the invoice becomes due, in the location time zone at the start of that day; -1 means its last day. Takes precedence over AutoCollectAfter, so leave this empty to date the due date from the invoice instead. Keep it at 28 or less so it exists in every month. |
| `--auto-collect-after` | int | Number of days after the invoice date the invoice becomes due; 0 means due immediately. Capped at 365 when the due date is calculated. Used only when AutoCollectOn is empty. |

#### TariffDefaultDueDate update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this plan due date. A rule also applies to invoices issued by locations further down the same network, because the lookup walks from the invoice location up to its root location. |
| `--tariffs` | list, repeat flag | List of plan IDs this due date applies to. An invoice matches when any of its contracts is on one of these plans. An empty list is not a disabled rule: it matches every invoice at the location, acting as a location-wide override of the default due date in Settings. |
| `--added-tariffs` | list, repeat flag | IDs added to the Tariffs relationship. |
| `--removed-tariffs` | list, repeat flag | IDs removed from the Tariffs relationship. |
| `--auto-collect-on` | int | Day of the FOLLOWING month the invoice becomes due, in the location time zone at the start of that day; -1 means its last day. Takes precedence over AutoCollectAfter, so leave this empty to date the due date from the invoice instead. Keep it at 28 or less so it exists in every month. |
| `--auto-collect-after` | int | Number of days after the invoice date the invoice becomes due; 0 means due immediately. Capped at 365 when the due date is calculated. Used only when AutoCollectOn is empty. |

### TariffDefaultDueDate (key fields)

`Id`, `AutoCollectOn`, `AutoCollectAfter`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

<!-- END:GENERATED entity=TariffDefaultDueDates -->
