# Surveys

<!-- BEGIN:GENERATED entity=Surveys -->

A survey (Survey) is a location-specific questionnaire sent to selected customers on a recurring schedule. It defines delivery timing, customer eligibility, and the questions customers can answer.

Surveys support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus surveys list --agent` | List all surveys |
| `nexudus surveys list --id <id> --agent` | Filter by single ID |
| `nexudus surveys list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus surveys list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus surveys list --business-id <value> --business-name <value> --agent` | Filter surveys by properties |
| `nexudus surveys list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus surveys list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus surveys get <id> --agent` | Get single survey |
| `nexudus surveys create --business-id <value> --name <value> --description <value> --next-delivery-date <value> --delivery-rate <value> --delivery-frequency <value> --delivery-rate-maximum <value> --agent` | Create survey |
| `nexudus surveys update <id> --name "New Name" --agent` | Update survey |
| `nexudus surveys delete <id> --yes --agent` | Delete survey (no prompt) |

#### Survey list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this survey; the Admin Tool normally supplies it from the current location context |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--business-web-address` | string |  |
| `--name` | string | Required name used by administrators to identify this survey |
| `--description` | string | Required free-text description explaining the purpose of this survey |
| `--active` | bool | Whether this survey is eligible for scheduled delivery when its next delivery date is due |
| `--next-delivery-date` | DateTime | UTC date and time when the next scheduled delivery is due; the system advances it by the delivery rate after a delivery |
| `--from-next-delivery-date` | range | |
| `--to-next-delivery-date` | range | |
| `--delivery-rate` | int | Positive number of delivery-frequency units between scheduled deliveries; a value of zero prevents scheduled delivery |
| `--from-delivery-rate` | range | |
| `--to-delivery-rate` | range | |
| `--delivery-frequency` | enum | Unit used by DeliveryRate and the delivery cap: Weeks, Months, or Years; defaults to Weeks |
| `--delivery-rate-maximum` | int | Maximum number of DeliveryFrequency units after StartDate for scheduled deliveries; zero means no end date |
| `--from-delivery-rate-maximum` | range | |
| `--to-delivery-rate-maximum` | range | |
| `--start-date` | DateTime | Optional UTC date and time from which the delivery cap is measured; without it, the delivery cap does not apply |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--only-for-contacts` | bool | Whether delivery is restricted to contacts without an active contract; when enabled with OnlyForMembers, both restrictions apply and no customer can qualify |
| `--only-for-members` | bool | Whether delivery is restricted to members with an active contract; when Tariffs is non-empty, the contract must be on one of those plans |
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
| `--business-id` | long, required | ID of the location that owns this survey; the Admin Tool normally supplies it from the current location context |
| `--name` | string, required | Required name used by administrators to identify this survey |
| `--description` | string, required | Required free-text description explaining the purpose of this survey |
| `--active` | bool | Whether this survey is eligible for scheduled delivery when its next delivery date is due |
| `--next-delivery-date` | DateTime, required | UTC date and time when the next scheduled delivery is due; the system advances it by the delivery rate after a delivery |
| `--delivery-rate` | int, required | Positive number of delivery-frequency units between scheduled deliveries; a value of zero prevents scheduled delivery |
| `--delivery-frequency` | enum, required | Unit used by DeliveryRate and the delivery cap: Weeks, Months, or Years; defaults to Weeks |
| `--delivery-rate-maximum` | int, required | Maximum number of DeliveryFrequency units after StartDate for scheduled deliveries; zero means no end date |
| `--start-date` | DateTime | Optional UTC date and time from which the delivery cap is measured; without it, the delivery cap does not apply |
| `--only-for-contacts` | bool | Whether delivery is restricted to contacts without an active contract; when enabled with OnlyForMembers, both restrictions apply and no customer can qualify |
| `--only-for-members` | bool | Whether delivery is restricted to members with an active contract; when Tariffs is non-empty, the contract must be on one of those plans |
| `--tariffs` | list, repeat flag | List of plans eligible for member-only delivery; when OnlyForMembers is enabled, an empty list allows every member, otherwise the customer needs an active contract on one of these plans |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this survey |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this survey |

#### Survey update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this survey; the Admin Tool normally supplies it from the current location context |
| `--name` | string | Required name used by administrators to identify this survey |
| `--description` | string | Required free-text description explaining the purpose of this survey |
| `--active` | bool | Whether this survey is eligible for scheduled delivery when its next delivery date is due |
| `--next-delivery-date` | DateTime | UTC date and time when the next scheduled delivery is due; the system advances it by the delivery rate after a delivery |
| `--delivery-rate` | int | Positive number of delivery-frequency units between scheduled deliveries; a value of zero prevents scheduled delivery |
| `--delivery-frequency` | enum | Unit used by DeliveryRate and the delivery cap: Weeks, Months, or Years; defaults to Weeks |
| `--delivery-rate-maximum` | int | Maximum number of DeliveryFrequency units after StartDate for scheduled deliveries; zero means no end date |
| `--start-date` | DateTime | Optional UTC date and time from which the delivery cap is measured; without it, the delivery cap does not apply |
| `--only-for-contacts` | bool | Whether delivery is restricted to contacts without an active contract; when enabled with OnlyForMembers, both restrictions apply and no customer can qualify |
| `--only-for-members` | bool | Whether delivery is restricted to members with an active contract; when Tariffs is non-empty, the contract must be on one of those plans |
| `--tariffs` | list, repeat flag | List of plans eligible for member-only delivery; when OnlyForMembers is enabled, an empty list allows every member, otherwise the customer needs an active contract on one of these plans |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this survey |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this survey |

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`

#### Survey enum values

| Option | Valid values |
| ------ | ------------ |
| `--delivery-frequency` | `1` Weeks, `2` Months, `3` Years |

<!-- END:GENERATED entity=Surveys -->
