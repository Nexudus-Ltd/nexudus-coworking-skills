# Surveys

<!-- BEGIN:GENERATED entity=Surveys -->

A **Survey** defines a questionnaire that can be delivered to customers on a schedule or triggered by specific events. Surveys support configurable delivery frequency and can target specific customer segments.

Surveys support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveys list --agent` | List all surveys |
| `nexudus surveys list --id <id> --agent` | Filter by single ID |
| `nexudus surveys list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveys list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveys list --business-id <value> --name <value> --agent` | Filter surveys by properties |
| `nexudus surveys list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveys list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus surveys get <id> --agent` | Get single survey |
| `nexudus surveys create --business-id <value> --name <value> --description <value> --next-delivery-date <value> --delivery-rate <value> --delivery-frequency <value> --delivery-rate-maximum <value> --delivery-frequency-maximum <value> --agent` | Create survey |
| `nexudus surveys update <id> --name "New Name" --agent` | Update survey |
| `nexudus surveys delete <id> --yes --agent` | Delete survey (no prompt) |

#### Survey list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this survey |
| `--description` | string | Free-text description of this survey |
| `--active` | bool | Whether this survey is currently active |
| `--next-delivery-date` | DateTime | Date/time value for next delivery date |
| `--from-next-delivery-date` | range | |
| `--to-next-delivery-date` | range | |
| `--delivery-rate` | int | The delivery rate value for this survey |
| `--from-delivery-rate` | range | |
| `--to-delivery-rate` | range | |
| `--delivery-frequency` | enum | The delivery frequency value for this survey |
| `--delivery-rate-maximum` | int | The delivery rate maximum value for this survey |
| `--from-delivery-rate-maximum` | range | |
| `--to-delivery-rate-maximum` | range | |
| `--delivery-frequency-maximum` | enum | The delivery frequency maximum value for this survey |
| `--start-date` | DateTime | Date/time value for start date |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Survey sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Survey create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this survey |
| `--description` | string, required | Free-text description of this survey |
| `--active` | bool | Whether this survey is currently active |
| `--next-delivery-date` | DateTime, required | Date/time value for next delivery date |
| `--delivery-rate` | int, required | The delivery rate value for this survey |
| `--delivery-frequency` | enum, required | The delivery frequency value for this survey |
| `--delivery-rate-maximum` | int, required | The delivery rate maximum value for this survey |
| `--delivery-frequency-maximum` | enum, required | The delivery frequency maximum value for this survey |
| `--start-date` | DateTime | Date/time value for start date |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this survey |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this survey |

#### Survey update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this survey |
| `--description` | string | Free-text description of this survey |
| `--active` | bool | Whether this survey is currently active |
| `--next-delivery-date` | DateTime | Date/time value for next delivery date |
| `--delivery-rate` | int | The delivery rate value for this survey |
| `--delivery-frequency` | enum | The delivery frequency value for this survey |
| `--delivery-rate-maximum` | int | The delivery rate maximum value for this survey |
| `--delivery-frequency-maximum` | enum | The delivery frequency maximum value for this survey |
| `--start-date` | DateTime | Date/time value for start date |
| `--only-for-contacts` | bool | Whether only for contacts is enabled |
| `--only-for-members` | bool | Whether only for members is enabled |
| `--tariffs` | list, repeat flag | List of tariffs linked to this record |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this survey |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this survey |

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

#### Survey enum values

| Option | Valid values |
| ------ | ------------ |
| `--delivery-frequency` | `1` Weeks, `2` Months, `3` Years |
| `--delivery-frequency-maximum` | `1` Weeks, `2` Months, `3` Years |

<!-- END:GENERATED entity=Surveys -->
