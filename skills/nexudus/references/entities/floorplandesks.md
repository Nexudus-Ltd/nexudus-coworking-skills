# FloorPlanDesks

<!-- BEGIN:GENERATED entity=FloorPlanDesks -->

A **FloorPlanDesk** (referred to as a *floor plan unit* in the UI) represents a specific area or room placed on a floor plan. Each unit typically maps to a bookable resource or a space assigned to a customer through a contract.

There are five unit types controlled by `ItemType`:

| ItemType       | Typical use                                                      |
| -------------- | ---------------------------------------------------------------- |
| Office         | Private office assigned to a customer via a contract             |
| DedicatedDesk  | Desk permanently assigned to a customer via a contract           |
| HotDesk        | Shared desk bookable via a resource or assigned to a contract    |
| Room           | Meeting room or bookable space linked to a resource              |
| Other          | Any area that does not match the types above                     |

Link a unit to a `Resource` via `ResourceId` to let customers book it through the floor plan view on the Members Portal. Assign it to one or more contracts via `CoworkerContractIds` to track occupancy.

Units can be monitored by an IoT sensor (`SensorId`). The last sensor reading is exposed via `SensorLastValue` and `IsSensorOccupied`.

Position and size on the canvas are maintained by the floor plan editor. `AvailableFromTime` / `AvailableToTime` allow time-bounded availability windows.

FloorPlanDesks support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplandesks list --agent` | List all floorplandesks |
| `nexudus floorplandesks list --id <id> --agent` | Filter by single ID |
| `nexudus floorplandesks list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplandesks list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplandesks list --name <value> --agent` | Filter floorplandesks by properties |
| `nexudus floorplandesks list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplandesks get <id> --agent` | Get single floorplandesk |
| `nexudus floorplandesks create --floor-plan-id <value> --name <value> --item-type <value> --size <value> --capacity <value> --price <value> --position-x <value> --position-y <value> --position-z <value> --agent` | Create floorplandesk |
| `nexudus floorplandesks update <id> --name "New Name" --agent` | Update floorplandesk |
| `nexudus floorplandesks delete <id> --yes --agent` | Delete floorplandesk (no prompt) |

#### FloorPlanDesk list filter options

`--floor-plan-id`, `--coworker-id`, `--sensor-id`, `--name`, `--item-type`, `--resource-id`, `--size`, `--from-size` (range), `--to-size` (range), `--size-is-linked-to-area`, `--capacity`, `--from-capacity` (range), `--to-capacity` (range), `--price`, `--from-price` (range), `--to-price` (range), `--area`, `--notes`, `--available`, `--position-x`, `--from-position-x` (range), `--to-position-x` (range), `--position-y`, `--from-position-y` (range), `--to-position-y` (range), `--position-z`, `--from-position-z` (range), `--to-position-z` (range), `--access-control-group-id`, `--tunnel-private-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--from-available-from-time` (range), `--to-available-from-time` (range), `--available-to-time`, `--from-available-to-time` (range), `--to-available-to-time` (range), `--available-from-time-local`, `--from-available-from-time-local` (range), `--to-available-from-time-local` (range), `--available-to-time-local`, `--from-available-to-time-local` (range), `--to-available-to-time-local` (range), `--archilogic-unique-id`, `--floor-plan-layout-asset-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanDesk create options

`--floor-plan-id` (required), `--coworker-id`, `--sensor-id`, `--name` (required), `--item-type` (required), `--resource-id`, `--size` (required), `--size-is-linked-to-area`, `--capacity` (required), `--price` (required), `--area`, `--notes`, `--available`, `--position-x` (required), `--position-y` (required), `--position-z` (required), `--access-control-group-id`, `--tunnel-private-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--available-to-time`, `--available-from-time-local`, `--available-to-time-local`, `--archilogic-unique-id`, `--floor-plan-layout-asset-unique-id`

#### FloorPlanDesk update options

`--floor-plan-id`, `--coworker-id`, `--sensor-id`, `--name`, `--item-type`, `--resource-id`, `--size`, `--size-is-linked-to-area`, `--capacity`, `--price`, `--area`, `--notes`, `--available`, `--position-x`, `--position-y`, `--position-z`, `--access-control-group-id`, `--tunnel-private-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--available-to-time`, `--available-from-time-local`, `--available-to-time-local`, `--archilogic-unique-id`, `--floor-plan-layout-asset-unique-id`

### FloorPlanDesk (key fields)

`Id`, `FloorPlanName`, `CoworkerFullName`, `SensorName`, `Name`, `ResourceName`

#### FloorPlanDesk enum values

| Option | Valid values |
| ------ | ------------ |
| `--item-type` | `1` Office, `2` DedicatedDesk, `3` HotDesk, `4` Other, `5` Room |

<!-- END:GENERATED entity=FloorPlanDesks -->
