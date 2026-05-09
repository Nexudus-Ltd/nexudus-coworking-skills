# Reminders

<!-- BEGIN:GENERATED entity=Reminders -->

Reminders support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus reminders list --agent` | List all reminders |
| `nexudus reminders list --id <id> --agent` | Filter by single ID |
| `nexudus reminders list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus reminders list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus reminders list --business-id <value> --name <value> --agent` | Filter reminders by properties |
| `nexudus reminders list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus reminders get <id> --agent` | Get single reminder |
| `nexudus reminders create --business-id <value> --name <value> --reminder-type <value> --reminder-action <value> --agent` | Create reminder |
| `nexudus reminders update <id> --name "New Name" --agent` | Update reminder |
| `nexudus reminders delete <id> --yes --agent` | Delete reminder (no prompt) |

#### Reminder list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--for-all-contacts` | bool |  |
| `--for-all-members` | bool |  |
| `--for-all-child-locations` | bool |  |
| `--coworker-id` | long |  |
| `--reminder-type` | enum |  |
| `--reminder-date` | DateTime |  |
| `--from-reminder-date` | range | |
| `--to-reminder-date` | range | |
| `--days-after-signup` | int |  |
| `--from-days-after-signup` | range | |
| `--to-days-after-signup` | range | |
| `--product-id` | long |  |
| `--survey-id` | long |  |
| `--days-after-renewal` | int |  |
| `--from-days-after-renewal` | range | |
| `--to-days-after-renewal` | range | |
| `--days-before-renewal` | int |  |
| `--from-days-before-renewal` | range | |
| `--to-days-before-renewal` | range | |
| `--reminder-action` | enum |  |
| `--email` | string |  |
| `--canned-response-id` | long |  |
| `--next-process-time` | DateTime |  |
| `--from-next-process-time` | range | |
| `--to-next-process-time` | range | |
| `--only-send-to-team-paying-members` | bool |  |
| `--only-send-to-active-coworkers` | bool |  |
| `--blocking-period-minutes` | int |  |
| `--from-blocking-period-minutes` | range | |
| `--to-blocking-period-minutes` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Reminder create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required |  |
| `--for-all-contacts` | bool |  |
| `--for-all-members` | bool |  |
| `--for-all-child-locations` | bool |  |
| `--coworker-id` | long |  |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--reminder-type` | enum, required |  |
| `--reminder-date` | DateTime |  |
| `--days-after-signup` | int |  |
| `--product-id` | long |  |
| `--survey-id` | long |  |
| `--days-after-renewal` | int |  |
| `--days-before-renewal` | int |  |
| `--reminder-action` | enum, required |  |
| `--email` | string |  |
| `--canned-response-id` | long |  |
| `--next-process-time` | DateTime |  |
| `--resources` | list, repeat flag |  |
| `--added-resources` | list, repeat flag |  |
| `--removed-resources` | list, repeat flag |  |
| `--only-send-to-team-paying-members` | bool |  |
| `--only-send-to-active-coworkers` | bool |  |
| `--blocking-period-minutes` | int |  |

#### Reminder update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string |  |
| `--for-all-contacts` | bool |  |
| `--for-all-members` | bool |  |
| `--for-all-child-locations` | bool |  |
| `--coworker-id` | long |  |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--reminder-type` | enum |  |
| `--reminder-date` | DateTime |  |
| `--days-after-signup` | int |  |
| `--product-id` | long |  |
| `--survey-id` | long |  |
| `--days-after-renewal` | int |  |
| `--days-before-renewal` | int |  |
| `--reminder-action` | enum |  |
| `--email` | string |  |
| `--canned-response-id` | long |  |
| `--next-process-time` | DateTime |  |
| `--resources` | list, repeat flag |  |
| `--added-resources` | list, repeat flag |  |
| `--removed-resources` | list, repeat flag |  |
| `--only-send-to-team-paying-members` | bool |  |
| `--only-send-to-active-coworkers` | bool |  |
| `--blocking-period-minutes` | int |  |

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=Reminders -->
