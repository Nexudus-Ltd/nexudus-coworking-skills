# RegisteredDevices

<!-- BEGIN:GENERATED entity=RegisteredDevices -->

A registered device is an integration hardware or software client associated with a location; operators can identify it, review its status, and enable or disable it.

RegisteredDevices support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus registereddevices list --agent` | List all registereddevices |
| `nexudus registereddevices list --id <id> --agent` | Filter by single ID |
| `nexudus registereddevices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus registereddevices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus registereddevices list --business-id <value> --name <value> --agent` | Filter registereddevices by properties |
| `nexudus registereddevices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus registereddevices list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus registereddevices get <id> --agent` | Get single registereddevice |
| `nexudus registereddevices update <id> --name "New Name" --agent` | Update registereddevice |

#### RegisteredDevice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location the device is associated with; association is managed by the device association workflow. |
| `--name` | string | Required operator-facing name used to identify the registered device. |
| `--device-type` | string | Read-only device type assigned during registration; it determines the device's authentication and permission behavior. |
| `--device-id` | string | Read-only unique identifier supplied by the device during registration and used for device authentication and messaging. |
| `--configuration-data` | string | Internal JSON configuration returned directly to the device; integration-specific and not available for agent use. |
| `--active` | bool | Whether the device can authenticate, associate with a location, send heartbeats, and submit logs; inactive devices cannot perform these operations. |
| `--last-heart-beat` | DateTime | Read-only UTC date and time of the most recent device registration, heartbeat, or log submission. |
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
| `--name` | string | Required operator-facing name used to identify the registered device. |
| `--configuration-data` | string | Internal JSON configuration returned directly to the device; integration-specific and not available for agent use. |
| `--active` | bool | Whether the device can authenticate, associate with a location, send heartbeats, and submit logs; inactive devices cannot perform these operations. |

<!-- END:GENERATED entity=RegisteredDevices -->
