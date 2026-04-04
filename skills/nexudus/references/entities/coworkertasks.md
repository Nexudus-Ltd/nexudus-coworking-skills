# CoworkerTasks

<!-- BEGIN:GENERATED entity=CoworkerTasks -->

CoworkerTasks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkertasks list --agent` | List all coworkertasks |
| `nexudus coworkertasks list --id <id> --agent` | Filter by single ID |
| `nexudus coworkertasks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkertasks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkertasks list --business-id <value> --coworker-id <value> --agent` | Filter coworkertasks by properties |
| `nexudus coworkertasks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkertasks get <id> --agent` | Get single coworkertask |
| `nexudus coworkertasks create --business-id <value> --coworker-id <value> --name <value> --responsible-id <value> --agent` | Create coworkertask |
| `nexudus coworkertasks update <id> --name "New Name" --agent` | Update coworkertask |
| `nexudus coworkertasks delete <id> --yes --agent` | Delete coworkertask (no prompt) |

#### CoworkerTask list filter options

`--business-id`, `--coworker-id`, `--name`, `--notes`, `--task-item-unique-id`, `--completed`, `--due-date`, `--reminded`, `--responsible-id`, `--notify-by-email`, `--display-to-everyone`, `--due-date-local`

#### CoworkerTask create options

`--business-id` (required), `--coworker-id` (required), `--name` (required), `--notes`, `--task-item-unique-id`, `--completed`, `--due-date`, `--reminded`, `--responsible-id` (required), `--notify-by-email`, `--display-to-everyone`, `--due-date-local`

#### CoworkerTask update options

`--business-id`, `--coworker-id`, `--name`, `--notes`, `--task-item-unique-id`, `--completed`, `--due-date`, `--reminded`, `--responsible-id`, `--notify-by-email`, `--display-to-everyone`, `--due-date-local`

<!-- END:GENERATED entity=CoworkerTasks -->
