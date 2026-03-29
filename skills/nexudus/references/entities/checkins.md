# Checkins

<!-- BEGIN:GENERATED entity=Checkins -->

Checkins support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus checkins list --agent` | List all checkins |
| `nexudus checkins list --query "search" --agent` | Search checkins by name |
| `nexudus checkins list --page 2 --size 10 --agent` | Paginated list |
| `nexudus checkins get <id> --agent` | Get single checkin |
| `nexudus checkins create --coworker-id <value> --business <value> --from-time <value> --agent` | Create checkin |
| `nexudus checkins update <id> --name "New Name" --agent` | Update checkin |
| `nexudus checkins delete <id> --yes --agent` | Delete checkin (no prompt) |

#### Checkin create options

`--coworker-id` (required), `--business` (required), `--source`, `--from-time` (required), `--to-time`, `--mac-addresses`

#### Checkin update options

`--coworker-id`, `--source`, `--from-time`, `--to-time`, `--mac-addresses`

### Checkin (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `BusinessId`, `BusinessName`, `Source`, `FromTime`, `ToTime`

#### Checkin enum values

| Option | Valid values |
| ------ | ------------ |
| `--source` | `1` Manual, `2` DoorAccess, `3` NetworkActivity, `4` Tile, `5` Sensor |

<!-- END:GENERATED entity=Checkins -->
