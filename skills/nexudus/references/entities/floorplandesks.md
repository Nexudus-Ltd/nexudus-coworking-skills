# FloorPlanDesks

<!-- BEGIN:GENERATED entity=FloorPlanDesks -->

FloorPlanDesks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplandesks list --agent` | List all floorplandesks |
| `nexudus floorplandesks list --id <id> --agent` | Filter by single ID |
| `nexudus floorplandesks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplandesks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplandesks list --floor-plan-id <value> --coworker-id <value> --agent` | Filter floorplandesks by properties |
| `nexudus floorplandesks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplandesks get <id> --agent` | Get single floorplandesk |
| `nexudus floorplandesks create --floor-plan-id <value> --name <value> --size <value> --capacity <value> --price <value> --position-x <value> --position-y <value> --position-z <value> --agent` | Create floorplandesk |
| `nexudus floorplandesks update <id> --name "New Name" --agent` | Update floorplandesk |
| `nexudus floorplandesks delete <id> --yes --agent` | Delete floorplandesk (no prompt) |

#### FloorPlanDesk list filter options

`--floor-plan-id`, `--coworker-id`, `--sensor-id`, `--name`, `--item-type`, `--resource-id`, `--size`, `--from-size` (range), `--to-size` (range), `--size-is-linked-to-area`, `--capacity`, `--from-capacity` (range), `--to-capacity` (range), `--price`, `--from-price` (range), `--to-price` (range), `--area`, `--notes`, `--available`, `--position-x`, `--from-position-x` (range), `--to-position-x` (range), `--position-y`, `--from-position-y` (range), `--to-position-y` (range), `--position-z`, `--from-position-z` (range), `--to-position-z` (range), `--access-control-group-id`, `--tunnel-private-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--from-available-from-time` (range), `--to-available-from-time` (range), `--available-to-time`, `--from-available-to-time` (range), `--to-available-to-time` (range), `--available-from-time-local`, `--from-available-from-time-local` (range), `--to-available-from-time-local` (range), `--available-to-time-local`, `--from-available-to-time-local` (range), `--to-available-to-time-local` (range), `--archilogic-unique-id`, `--floor-plan-layout-asset-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanDesk create options

`--floor-plan-id` (required), `--coworker-id`, `--sensor-id`, `--name` (required), `--item-type`, `--resource-id`, `--size` (required), `--size-is-linked-to-area`, `--capacity` (required), `--price` (required), `--area`, `--notes`, `--available`, `--position-x` (required), `--position-y` (required), `--position-z` (required), `--access-control-group-id`, `--tunnel-private-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--available-to-time`, `--available-from-time-local`, `--available-to-time-local`, `--archilogic-unique-id`, `--floor-plan-layout-asset-unique-id`

#### FloorPlanDesk update options

`--floor-plan-id`, `--coworker-id`, `--sensor-id`, `--name`, `--item-type`, `--resource-id`, `--size`, `--size-is-linked-to-area`, `--capacity`, `--price`, `--area`, `--notes`, `--available`, `--position-x`, `--position-y`, `--position-z`, `--access-control-group-id`, `--tunnel-private-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--available-to-time`, `--available-from-time-local`, `--available-to-time-local`, `--archilogic-unique-id`, `--floor-plan-layout-asset-unique-id`

<!-- END:GENERATED entity=FloorPlanDesks -->
