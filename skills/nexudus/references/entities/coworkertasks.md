# CoworkerTasks

<!-- BEGIN:GENERATED entity=CoworkerTasks -->

A task is an operational to-do item for a customer, assigned to an admin user with optional due-date email reminders and visibility to the wider admin team.

CoworkerTasks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkertasks list --agent` | List all coworkertasks |
| `nexudus coworkertasks list --id <id> --agent` | Filter by single ID |
| `nexudus coworkertasks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkertasks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkertasks list --business-name <value> --coworker-full-name <value> --agent` | Filter coworkertasks by properties |
| `nexudus coworkertasks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkertasks list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkertasks get <id> --agent` | Get single coworkertask |
| `nexudus coworkertasks create --business-id <value> --coworker-id <value> --name <value> --responsible-id <value> --agent` | Create coworkertask |
| `nexudus coworkertasks update <id> --name "New Name" --agent` | Update coworkertask |
| `nexudus coworkertasks delete <id> --yes --agent` | Delete coworkertask (no prompt) |

#### CoworkerTask list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this task. |
| `--business-name` | string | Display value for Business.Name. |
| `--coworker-id` | long | ID of the customer this task concerns. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-team-names` | string | Display value for Coworker.TeamNames. |
| `--name` | string | Required task title. |
| `--notes` | string | Optional instructions or context for completing the task. |
| `--task-list-name` | string | Read-only name of the task list from which this task was created, when applicable. |
| `--completed` | bool | Whether the task is complete; completed tasks are excluded from reminder processing and each user's active-task list. |
| `--due-date` | DateTime | Optional due date and time stored in UTC; an email reminder becomes eligible at or after this time when notifications are enabled. |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--responsible-id` | long | ID of the admin user responsible for completing this task; required when creating a task. |
| `--responsible-full-name` | string | Display value for Responsible.FullName. |
| `--notify-by-email` | bool | Whether to send the responsible admin an email reminder once the due date is reached; no reminder is sent without a due date. |
| `--display-to-everyone` | bool | Whether the task appears in every admin user's active-task list instead of only the responsible admin's list. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerTask sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `DueDate` ascending. If no `--order-by` is specified, the API returns results ordered by `DueDate` (ascending).

#### CoworkerTask create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this task. |
| `--coworker-id` | long, required | ID of the customer this task concerns. |
| `--name` | string, required | Required task title. |
| `--notes` | string | Optional instructions or context for completing the task. |
| `--completed` | bool | Whether the task is complete; completed tasks are excluded from reminder processing and each user's active-task list. |
| `--due-date` | DateTime | Optional due date and time stored in UTC; an email reminder becomes eligible at or after this time when notifications are enabled. |
| `--responsible-id` | long, required | ID of the admin user responsible for completing this task; required when creating a task. |
| `--notify-by-email` | bool | Whether to send the responsible admin an email reminder once the due date is reached; no reminder is sent without a due date. |
| `--display-to-everyone` | bool | Whether the task appears in every admin user's active-task list instead of only the responsible admin's list. |

#### CoworkerTask update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this task. |
| `--coworker-id` | long | ID of the customer this task concerns. |
| `--name` | string | Required task title. |
| `--notes` | string | Optional instructions or context for completing the task. |
| `--completed` | bool | Whether the task is complete; completed tasks are excluded from reminder processing and each user's active-task list. |
| `--due-date` | DateTime | Optional due date and time stored in UTC; an email reminder becomes eligible at or after this time when notifications are enabled. |
| `--responsible-id` | long | ID of the admin user responsible for completing this task; required when creating a task. |
| `--notify-by-email` | bool | Whether to send the responsible admin an email reminder once the due date is reached; no reminder is sent without a due date. |
| `--display-to-everyone` | bool | Whether the task appears in every admin user's active-task list instead of only the responsible admin's list. |

#### CoworkerTask PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notify-by-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus coworkertasks update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerTask (key fields)

`Id`, `BusinessName`, `CoworkerFullName`, `Name`, `TaskListName`, `Completed`, `ResponsibleFullName`

<!-- END:GENERATED entity=CoworkerTasks -->
