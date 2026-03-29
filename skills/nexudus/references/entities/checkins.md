# Checkins

<!-- BEGIN:GENERATED entity=Checkins -->

A **Checkin** records when a customer accessed a location. To check in, a customer must hold a valid pass (`TimePass` entity) that covers the location and the time of the check-in.

If the customer does not have a valid pass but the location or network has one or more **Pay As You Go** passes configured, a pass is automatically assigned and charged to the customer at check-in time.

Check-ins can be created manually, or opened and closed automatically by **NexIO** (the front-desk Nexudus tablet app), door-access systems, or IT-network integrations. The `Source` field indicates how the check-in was created.

Checkins support Search, Get, Create, Update, Delete.
Checkins also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus checkins list --agent` | List all checkins |
| `nexudus checkins list --query "search" --agent` | Search checkins by name |
| `nexudus checkins list --page 2 --size 10 --agent` | Paginated list |
| `nexudus checkins get <id> --agent` | Get single checkin |
| `nexudus checkins create --coworker-id <value> --business <value> --from-time <value> --agent` | Create checkin |
| `nexudus checkins update <id> --name "New Name" --agent` | Update checkin |
| `nexudus checkins delete <id> --yes --agent` | Delete checkin (no prompt) |
| `nexudus checkins run-command <key> <ids> --agent` | Run entity command |

#### Checkin create options

`--coworker-id` (required), `--business` (required), `--source`, `--from-time` (required), `--to-time`, `--mac-addresses`

#### Checkin update options

`--coworker-id`, `--source`, `--from-time`, `--to-time`, `--mac-addresses`

### Checkin (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `BusinessId`, `BusinessName`, `Source`, `FromTime`, `ToTime`

#### Checkin enum values

| Option | Valid values |
| ------ | ------------ |
| `--source` | `0` None, `1` Manual, `2` DoorAccess, `3` NetworkActivity, `4` Tile, `5` Sensor |

<!-- END:GENERATED entity=Checkins -->
