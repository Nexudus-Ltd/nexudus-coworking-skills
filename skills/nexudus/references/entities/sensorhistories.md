# SensorHistories

<!-- BEGIN:GENERATED entity=SensorHistories -->

SensorHistories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus sensorhistories list --agent` | List all sensorhistories |
| `nexudus sensorhistories list --id <id> --agent` | Filter by single ID |
| `nexudus sensorhistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus sensorhistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus sensorhistories list --sensor-id <value> --value <value> --agent` | Filter sensorhistories by properties |
| `nexudus sensorhistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus sensorhistories get <id> --agent` | Get single sensorhistory |
| `nexudus sensorhistories create --sensor-id <value> --observed-on <value> --agent` | Create sensorhistory |
| `nexudus sensorhistories update <id> --name "New Name" --agent` | Update sensorhistory |
| `nexudus sensorhistories delete <id> --yes --agent` | Delete sensorhistory (no prompt) |

#### SensorHistory list filter options

`--sensor-id`, `--value`, `--observed-on`

#### SensorHistory create options

`--sensor-id` (required), `--value`, `--observed-on` (required)

#### SensorHistory update options

`--sensor-id`, `--value`, `--observed-on`

<!-- END:GENERATED entity=SensorHistories -->
