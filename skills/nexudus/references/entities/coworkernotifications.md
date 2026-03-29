# CoworkerNotifications

<!-- BEGIN:GENERATED entity=CoworkerNotifications -->

CoworkerNotifications support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkernotifications list --agent` | List all coworkernotifications |
| `nexudus coworkernotifications list --query "search" --agent` | Search coworkernotifications by name |
| `nexudus coworkernotifications list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkernotifications get <id> --agent` | Get single coworkernotification |
| `nexudus coworkernotifications create --coworker-id <value> --message <value> --agent` | Create coworkernotification |
| `nexudus coworkernotifications update <id> --name "New Name" --agent` | Update coworkernotification |
| `nexudus coworkernotifications delete <id> --yes --agent` | Delete coworkernotification (no prompt) |

#### CoworkerNotification create options

`--coworker-id` (required), `--message` (required), `--notification-type`, `--entity-id`, `--is-dismissed`

#### CoworkerNotification update options

`--coworker-id`, `--message`, `--notification-type`, `--entity-id`, `--is-dismissed`

### CoworkerNotification (key fields)

`Id`, `CoworkerId`, `Message`

<!-- END:GENERATED entity=CoworkerNotifications -->
