# RadiusServers

<!-- BEGIN:GENERATED entity=RadiusServers -->

RadiusServers support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus radiusservers list --agent` | List all radiusservers |
| `nexudus radiusservers list --id <id> --agent` | Filter by single ID |
| `nexudus radiusservers list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus radiusservers list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus radiusservers list --business-id <value> --name <value> --agent` | Filter radiusservers by properties |
| `nexudus radiusservers list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus radiusservers get <id> --agent` | Get single radiusserver |
| `nexudus radiusservers create --business-id <value> --name <value> --agent` | Create radiusserver |
| `nexudus radiusservers update <id> --name "New Name" --agent` | Update radiusserver |
| `nexudus radiusservers delete <id> --yes --agent` | Delete radiusserver (no prompt) |

#### RadiusServer list filter options

`--business-id`, `--name`, `--vendor`, `--active`, `--description`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### RadiusServer create options

`--business-id` (required), `--name` (required), `--vendor`, `--active`, `--description`

#### RadiusServer update options

`--business-id`, `--name`, `--vendor`, `--active`, `--description`

<!-- END:GENERATED entity=RadiusServers -->
