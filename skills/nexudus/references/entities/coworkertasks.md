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
| `nexudus coworkertasks list --name <value> --completed <value> --agent` | Filter coworkertasks by properties |
| `nexudus coworkertasks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkertasks get <id> --agent` | Get single coworkertask |
| `nexudus coworkertasks create --business-id <value> --coworker-id <value> --name <value> --responsible-id <value> --agent` | Create coworkertask |
| `nexudus coworkertasks update <id> --name "New Name" --agent` | Update coworkertask |
| `nexudus coworkertasks delete <id> --yes --agent` | Delete coworkertask (no prompt) |

#### CoworkerTask list filter options

`--business-id` (long), `--coworker-id` (long), `--name`, `--notes`, `--task-item-unique-id`, `--completed` (bool), `--due-date` (DateTime), `--from-due-date` (range), `--to-due-date` (range), `--reminded` (bool), `--responsible-id` (long), `--notify-by-email` (bool), `--display-to-everyone` (bool), `--due-date-local` (DateTime), `--from-due-date-local` (range), `--to-due-date-local` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerTask create options

`--business-id` (long, required), `--coworker-id` (long, required), `--name` (required), `--notes`, `--task-item-unique-id`, `--completed` (bool), `--due-date` (DateTime), `--reminded` (bool), `--responsible-id` (long, required), `--notify-by-email` (bool), `--display-to-everyone` (bool), `--due-date-local` (DateTime)

#### CoworkerTask update options

`--business-id` (long), `--coworker-id` (long), `--name`, `--notes`, `--task-item-unique-id`, `--completed` (bool), `--due-date` (DateTime), `--reminded` (bool), `--responsible-id` (long), `--notify-by-email` (bool), `--display-to-everyone` (bool), `--due-date-local` (DateTime)

### CoworkerTask (key fields)

`Id`, `BusinessName`, `CoworkerFullName`, `Name`, `TaskListName`, `Completed`, `ResponsibleFullName`

<!-- END:GENERATED entity=CoworkerTasks -->
