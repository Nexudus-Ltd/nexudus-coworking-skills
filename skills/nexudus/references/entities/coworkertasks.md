# CoworkerTasks

<!-- BEGIN:GENERATED entity=CoworkerTasks -->

A **CoworkerTask** represents a to-do item that can be assigned to an admin user. Tasks help space managers and staff track daily operations such as onboarding steps, maintenance requests, or follow-ups.

Each task is linked to a customer (`CoworkerId`) and assigned to a responsible admin (`ResponsibleId`). The responsible admin receives a notification on the Admin Panel and can mark the task as completed once done.

Tasks can optionally be grouped into task lists (`TaskListName`). Task lists standardise and partially automate admin processes — for example, a series of onboarding tasks (access card handout, locker keys, welcome tour) each assigned to a different admin.

Use `NotifyByEmail` to send an email reminder to the responsible admin when the task is due. Use `DisplayToEveryone` to make the task visible to all admin users, not just the responsible one.

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
| `--business-id` | long | ID of the business linked to this record |
| `--business-name` | string | Location name |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--coworker-full-name` | string | Customer full name |
| `--coworker-company-name` | string | Customer company name |
| `--coworker-team-names` | string | Customer team names |
| `--name` | string | Task name |
| `--notes` | string | Additional details or instructions for the task |
| `--task-list-name` | string | Name of the task list this task belongs to |
| `--task-item-unique-id` | string | Unique identifier of the task item within a task list |
| `--form-page-request-unique-id` | string | Unique identifier of the form page request that created this task |
| `--completed` | bool | Whether the task has been marked as completed |
| `--due-date` | DateTime | Due date for the task (UTC) |
| `--from-due-date` | range | |
| `--to-due-date` | range | |
| `--reminded` | bool | Whether a reminder has been sent for this task |
| `--responsible-id` | long | ID of the responsible linked to this record |
| `--responsible-full-name` | string | Responsible admin full name |
| `--notify-by-email` | bool | Whether to notify the responsible admin by email when the task is due |
| `--display-to-everyone` | bool | Whether the task is visible to all admin users |
| `--due-date-local` | DateTime | Due date for the task in the location's local timezone |
| `--from-due-date-local` | range | |
| `--to-due-date-local` | range | |
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
| `--business-id` | long, required | ID of the business linked to this record |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--name` | string, required | Task name |
| `--notes` | string | Additional details or instructions for the task |
| `--task-item-unique-id` | string | Unique identifier of the task item within a task list |
| `--completed` | bool | Whether the task has been marked as completed |
| `--due-date` | DateTime | Due date for the task (UTC) |
| `--reminded` | bool | Whether a reminder has been sent for this task |
| `--responsible-id` | long, required | ID of the responsible linked to this record |
| `--notify-by-email` | bool | Whether to notify the responsible admin by email when the task is due |
| `--display-to-everyone` | bool | Whether the task is visible to all admin users |
| `--due-date-local` | DateTime | Due date for the task in the location's local timezone |

#### CoworkerTask update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--name` | string | Task name |
| `--notes` | string | Additional details or instructions for the task |
| `--task-item-unique-id` | string | Unique identifier of the task item within a task list |
| `--completed` | bool | Whether the task has been marked as completed |
| `--due-date` | DateTime | Due date for the task (UTC) |
| `--reminded` | bool | Whether a reminder has been sent for this task |
| `--responsible-id` | long | ID of the responsible linked to this record |
| `--notify-by-email` | bool | Whether to notify the responsible admin by email when the task is due |
| `--display-to-everyone` | bool | Whether the task is visible to all admin users |
| `--due-date-local` | DateTime | Due date for the task in the location's local timezone |

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
