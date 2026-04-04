# CoworkerSettings

<!-- BEGIN:GENERATED entity=CoworkerSettings -->

CoworkerSettings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkersettings list --agent` | List all coworkersettings |
| `nexudus coworkersettings list --id <id> --agent` | Filter by single ID |
| `nexudus coworkersettings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkersettings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkersettings list --coworker-id <value> --name <value> --agent` | Filter coworkersettings by properties |
| `nexudus coworkersettings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkersettings get <id> --agent` | Get single coworkersetting |
| `nexudus coworkersettings create --coworker-id <value> --name <value> --agent` | Create coworkersetting |
| `nexudus coworkersettings update <id> --name "New Name" --agent` | Update coworkersetting |
| `nexudus coworkersettings delete <id> --yes --agent` | Delete coworkersetting (no prompt) |

#### CoworkerSetting list filter options

`--coworker-id`, `--name`, `--value`, `--encrypted-value`

#### CoworkerSetting create options

`--coworker-id` (required), `--name` (required), `--value`, `--encrypted-value`

#### CoworkerSetting update options

`--coworker-id`, `--name`, `--value`, `--encrypted-value`

<!-- END:GENERATED entity=CoworkerSettings -->
