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
| `nexudus reminders create --business-id <value> --name <value> --agent` | Create reminder |
| `nexudus reminders update <id> --name "New Name" --agent` | Update reminder |
| `nexudus reminders delete <id> --yes --agent` | Delete reminder (no prompt) |

#### Reminder list filter options

`--business-id`, `--name`, `--for-all-contacts`, `--for-all-members`, `--for-all-child-locations`, `--coworker-id`, `--reminder-type`, `--reminder-date`, `--from-reminder-date` (range), `--to-reminder-date` (range), `--days-after-signup`, `--from-days-after-signup` (range), `--to-days-after-signup` (range), `--product-id`, `--survey-id`, `--days-after-renewal`, `--from-days-after-renewal` (range), `--to-days-after-renewal` (range), `--days-before-renewal`, `--from-days-before-renewal` (range), `--to-days-before-renewal` (range), `--reminder-action`, `--email`, `--canned-response-id`, `--next-process-time`, `--from-next-process-time` (range), `--to-next-process-time` (range), `--only-send-to-team-paying-members`, `--only-send-to-active-coworkers`, `--blocking-period-minutes`, `--from-blocking-period-minutes` (range), `--to-blocking-period-minutes` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Reminder create options

`--business-id` (required), `--name` (required), `--for-all-contacts`, `--for-all-members`, `--for-all-child-locations`, `--coworker-id`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--reminder-type`, `--reminder-date`, `--days-after-signup`, `--product-id`, `--survey-id`, `--days-after-renewal`, `--days-before-renewal`, `--reminder-action`, `--email`, `--canned-response-id`, `--next-process-time`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--only-send-to-team-paying-members`, `--only-send-to-active-coworkers`, `--blocking-period-minutes`

#### Reminder update options

`--business-id`, `--name`, `--for-all-contacts`, `--for-all-members`, `--for-all-child-locations`, `--coworker-id`, `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--reminder-type`, `--reminder-date`, `--days-after-signup`, `--product-id`, `--survey-id`, `--days-after-renewal`, `--days-before-renewal`, `--reminder-action`, `--email`, `--canned-response-id`, `--next-process-time`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--only-send-to-team-paying-members`, `--only-send-to-active-coworkers`, `--blocking-period-minutes`

**List properties (only returned by `get`, not by `list`):** `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=Reminders -->
