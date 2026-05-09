# RegisteredDevices

<!-- BEGIN:GENERATED entity=RegisteredDevices -->

RegisteredDevices support Search, Get, Update (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus registereddevices list --agent` | List all registereddevices |
| `nexudus registereddevices list --id <id> --agent` | Filter by single ID |
| `nexudus registereddevices list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus registereddevices list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus registereddevices list --name <value> --configuration-data <value> --agent` | Filter registereddevices by properties |
| `nexudus registereddevices list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus registereddevices get <id> --agent` | Get single registereddevice |
| `nexudus registereddevices update <id> --name "New Name" --agent` | Update registereddevice |

#### RegisteredDevice list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--configuration-data` | string |  |
| `--active` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### RegisteredDevice update options

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--configuration-data` | string |  |
| `--active` | bool |  |

<!-- END:GENERATED entity=RegisteredDevices -->
