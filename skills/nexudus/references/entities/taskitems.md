# TaskItems

<!-- BEGIN:GENERATED entity=TaskItems -->

A task is one step of a task list: a template that is copied into a customer task, due a set number of hours later, every time the list is applied to a customer.

TaskItems support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus taskitems list --agent` | List all taskitems |
| `nexudus taskitems list --id <id> --agent` | Filter by single ID |
| `nexudus taskitems list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus taskitems list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus taskitems list --task-list-id <value> --responsible-id <value> --agent` | Filter taskitems by properties |
| `nexudus taskitems list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus taskitems list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus taskitems get <id> --agent` | Get single taskitem |
| `nexudus taskitems create --task-list-id <value> --responsible-id <value> --name <value> --delay-in-hours <value> --agent` | Create taskitem |
| `nexudus taskitems update <id> --name "New Name" --agent` | Update taskitem |
| `nexudus taskitems delete <id> --yes --agent` | Delete taskitem (no prompt) |

#### TaskItem list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--task-list-id` | long | ID of the task list this task belongs to; it is required, and it also decides the owning location because a task has no location of its own |
| `--responsible-id` | long | ID of the admin user accountable for this task; it is required, and it is copied onto every customer task created from this one unless the workflow applying the list supplies its own responsible user |
| `--responsible-full-name` | string | Display value for Responsible.FullName. |
| `--name` | string | Title of the task, copied onto every customer task created from this one; required |
| `--active` | bool | Whether this task is copied when its task list is applied to a customer; an inactive task is skipped, and customer tasks already created from it are left alone |
| `--notify-by-email` | bool | Whether the responsible admin user is emailed about the customer tasks created from this one; it is copied onto each of them, notifying the responsible user when the task is assigned and again when it falls due. Saving this template task never emails anybody |
| `--display-to-everyone` | bool | Whether customer tasks created from this one appear in every admin user's active task list at the location instead of only the responsible user's |
| `--delay-in-hours` | int | Whole hours between the task list being applied and the resulting customer task falling due, counted in UTC from the moment it is applied: 0 is due immediately and 48 is due two days later; a negative value back-dates the due date, and this is also the default order of the tasks in a list |
| `--from-delay-in-hours` | range | |
| `--to-delay-in-hours` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### TaskItem sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `DelayInHours` ascending. If no `--order-by` is specified, the API returns results ordered by `DelayInHours` (ascending).

#### TaskItem create options

| Option | Type | Description |
| --- | --- | --- |
| `--task-list-id` | long, required | ID of the task list this task belongs to; it is required, and it also decides the owning location because a task has no location of its own |
| `--responsible-id` | long, required | ID of the admin user accountable for this task; it is required, and it is copied onto every customer task created from this one unless the workflow applying the list supplies its own responsible user |
| `--name` | string, required | Title of the task, copied onto every customer task created from this one; required |
| `--active` | bool | Whether this task is copied when its task list is applied to a customer; an inactive task is skipped, and customer tasks already created from it are left alone |
| `--notify-by-email` | bool | Whether the responsible admin user is emailed about the customer tasks created from this one; it is copied onto each of them, notifying the responsible user when the task is assigned and again when it falls due. Saving this template task never emails anybody |
| `--display-to-everyone` | bool | Whether customer tasks created from this one appear in every admin user's active task list at the location instead of only the responsible user's |
| `--delay-in-hours` | int, required | Whole hours between the task list being applied and the resulting customer task falling due, counted in UTC from the moment it is applied: 0 is due immediately and 48 is due two days later; a negative value back-dates the due date, and this is also the default order of the tasks in a list |

#### TaskItem update options

| Option | Type | Description |
| --- | --- | --- |
| `--task-list-id` | long | ID of the task list this task belongs to; it is required, and it also decides the owning location because a task has no location of its own |
| `--responsible-id` | long | ID of the admin user accountable for this task; it is required, and it is copied onto every customer task created from this one unless the workflow applying the list supplies its own responsible user |
| `--name` | string | Title of the task, copied onto every customer task created from this one; required |
| `--active` | bool | Whether this task is copied when its task list is applied to a customer; an inactive task is skipped, and customer tasks already created from it are left alone |
| `--notify-by-email` | bool | Whether the responsible admin user is emailed about the customer tasks created from this one; it is copied onto each of them, notifying the responsible user when the task is assigned and again when it falls due. Saving this template task never emails anybody |
| `--display-to-everyone` | bool | Whether customer tasks created from this one appear in every admin user's active task list at the location instead of only the responsible user's |
| `--delay-in-hours` | int | Whole hours between the task list being applied and the resulting customer task falling due, counted in UTC from the moment it is applied: 0 is due immediately and 48 is due two days later; a negative value back-dates the due date, and this is also the default order of the tasks in a list |

#### TaskItem PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notify-by-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |

Example:

`nexudus taskitems update <id> --responsible-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=TaskItems -->
