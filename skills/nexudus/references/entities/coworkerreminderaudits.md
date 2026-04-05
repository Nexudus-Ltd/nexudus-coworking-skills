# CoworkerReminderAudits

<!-- BEGIN:GENERATED entity=CoworkerReminderAudits -->

CoworkerReminderAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerreminderaudits list --agent` | List all coworkerreminderaudits |
| `nexudus coworkerreminderaudits list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerreminderaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerreminderaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerreminderaudits list --coworker-id <value> --reminder-id <value> --agent` | Filter coworkerreminderaudits by properties |
| `nexudus coworkerreminderaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerreminderaudits get <id> --agent` | Get single coworkerreminderaudit |
| `nexudus coworkerreminderaudits create --coworker-id <value> --reminder-id <value> --agent` | Create coworkerreminderaudit |
| `nexudus coworkerreminderaudits update <id> --name "New Name" --agent` | Update coworkerreminderaudit |
| `nexudus coworkerreminderaudits delete <id> --yes --agent` | Delete coworkerreminderaudit (no prompt) |

#### CoworkerReminderAudit list filter options

`--coworker-id`, `--reminder-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerReminderAudit create options

`--coworker-id` (required), `--reminder-id` (required)

#### CoworkerReminderAudit update options

`--coworker-id`, `--reminder-id`

<!-- END:GENERATED entity=CoworkerReminderAudits -->
