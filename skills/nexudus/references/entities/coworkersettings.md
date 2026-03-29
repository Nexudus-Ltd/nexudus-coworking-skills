# CoworkerSettings

<!-- BEGIN:GENERATED entity=CoworkerSettings -->

CoworkerSettings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkersettings list --agent` | List all coworkersettings |
| `nexudus coworkersettings list --query "search" --agent` | Search coworkersettings by name |
| `nexudus coworkersettings list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkersettings get <id> --agent` | Get single coworkersetting |
| `nexudus coworkersettings create --coworker-id <value> --name <value> --agent` | Create coworkersetting |
| `nexudus coworkersettings update <id> --name "New Name" --agent` | Update coworkersetting |
| `nexudus coworkersettings delete <id> --yes --agent` | Delete coworkersetting (no prompt) |

#### CoworkerSetting create options

`--coworker-id` (required), `--name` (required), `--value`, `--encrypted-value`

#### CoworkerSetting update options

`--coworker-id`, `--name`, `--value`, `--encrypted-value`

### CoworkerSetting (key fields)

`Id`, `CoworkerId`, `Name`

<!-- END:GENERATED entity=CoworkerSettings -->
