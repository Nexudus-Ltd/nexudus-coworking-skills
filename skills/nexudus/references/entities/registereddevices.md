# RegisteredDevices

<!-- BEGIN:GENERATED entity=RegisteredDevices -->

A **RegisteredDevice** represents a device (phone, laptop, tablet) registered by a customer for network access, push notifications, or check-in purposes.

RegisteredDevices support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus registereddevices list --agent` | List all registereddevices |
| `nexudus registereddevices list --id <id> --agent` | Filter by single ID |
| `nexudus registereddevices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus registereddevices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus registereddevices list --business-id <value> --user-id <value> --agent` | Filter registereddevices by properties |
| `nexudus registereddevices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus registereddevices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus registereddevices get <id> --agent` | Get single registereddevice |
| `nexudus registereddevices update <id> --name "New Name" --agent` | Update registereddevice |

#### RegisteredDevice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--user-id` | long | ID of the user linked to this record |
| `--name` | string | The name value for this registered device |
| `--device-type` | string | The device type value for this registered device |
| `--device-id` | string | ID of the device associated with this record |
| `--configuration-data` | string | The configuration data value for this registered device |
| `--active` | bool | Whether this registered device is currently active |
| `--last-heart-beat` | DateTime | Date/time value for last heart beat |
| `--from-last-heart-beat` | range | |
| `--to-last-heart-beat` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RegisteredDevice sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### RegisteredDevice update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string | The name value for this registered device |
| `--configuration-data` | string | The configuration data value for this registered device |
| `--active` | bool | Whether this registered device is currently active |

<!-- END:GENERATED entity=RegisteredDevices -->
