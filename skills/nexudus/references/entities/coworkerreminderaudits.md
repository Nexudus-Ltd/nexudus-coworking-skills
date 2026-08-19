# CoworkerReminderAudits

<!-- BEGIN:GENERATED entity=CoworkerReminderAudits -->

A **CoworkerReminderAudit** records when a reminder was sent to a customer at a location. Each entry links the customer to the reminder that was triggered, forming an internal audit trail of automated communications that have been dispatched.

Use these records to determine which reminders have already been sent to a specific customer, and to avoid sending duplicate communications.

CoworkerReminderAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerreminderaudits list --agent` | List all coworkerreminderaudits |
| `nexudus coworkerreminderaudits list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerreminderaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerreminderaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerreminderaudits list --coworker-full-name <value> --reminder-name <value> --agent` | Filter coworkerreminderaudits by properties |
| `nexudus coworkerreminderaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerreminderaudits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerreminderaudits get <id> --agent` | Get single coworkerreminderaudit |
| `nexudus coworkerreminderaudits create --coworker-id <value> --reminder-id <value> --agent` | Create coworkerreminderaudit |
| `nexudus coworkerreminderaudits update <id> --name "New Name" --agent` | Update coworkerreminderaudit |
| `nexudus coworkerreminderaudits delete <id> --yes --agent` | Delete coworkerreminderaudit (no prompt) |

#### CoworkerReminderAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer the reminder was sent to |
| `--coworker-full-name` | string | Full name of the customer the reminder was sent to |
| `--reminder-id` | long | ID of the reminder that was sent |
| `--reminder-name` | string | Name of the reminder that was sent |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerReminderAudit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` descending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (descending).

#### CoworkerReminderAudit create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer the reminder was sent to |
| `--reminder-id` | long, required | ID of the reminder that was sent |

#### CoworkerReminderAudit update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer the reminder was sent to |
| `--reminder-id` | long | ID of the reminder that was sent |

#### CoworkerReminderAudit PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus coworkerreminderaudits update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerReminderAudit (key fields)

`Id`, `CoworkerFullName`, `ReminderName`

<!-- END:GENERATED entity=CoworkerReminderAudits -->
