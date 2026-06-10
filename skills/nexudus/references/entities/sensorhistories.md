# SensorHistories

<!-- BEGIN:GENERATED entity=SensorHistories -->

A **SensorHistory** record stores a historical data point from a sensor reading, including the measured value and timestamp. History records enable trend analysis and reporting on environmental conditions over time.

SensorHistories support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus sensorhistories list --agent` | List all sensorhistories |
| `nexudus sensorhistories list --id <id> --agent` | Filter by single ID |
| `nexudus sensorhistories list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus sensorhistories list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus sensorhistories list --sensor-id <value> --value <value> --agent` | Filter sensorhistories by properties |
| `nexudus sensorhistories list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus sensorhistories list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus sensorhistories get <id> --agent` | Get single sensorhistory |
| `nexudus sensorhistories create --sensor-id <value> --observed-on <value> --agent` | Create sensorhistory |
| `nexudus sensorhistories update <id> --name "New Name" --agent` | Update sensorhistory |
| `nexudus sensorhistories delete <id> --yes --agent` | Delete sensorhistory (no prompt) |

#### SensorHistory list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--sensor-id` | long | ID of the sensor linked to this record |
| `--value` | string | The value value for this sensor history |
| `--observed-on` | DateTime | Date/time value for observed on |
| `--from-observed-on` | range | |
| `--to-observed-on` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### SensorHistory sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### SensorHistory create options

| Option | Type | Description |
| --- | --- | --- |
| `--sensor-id` | long, required | ID of the sensor linked to this record |
| `--value` | string | The value value for this sensor history |
| `--observed-on` | DateTime, required | Date/time value for observed on |

#### SensorHistory update options

| Option | Type | Description |
| --- | --- | --- |
| `--sensor-id` | long | ID of the sensor linked to this record |
| `--value` | string | The value value for this sensor history |
| `--observed-on` | DateTime | Date/time value for observed on |

<!-- END:GENERATED entity=SensorHistories -->
