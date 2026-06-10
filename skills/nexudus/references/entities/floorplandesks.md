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
| `nexudus floorplandesks list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplandesks get <id> --agent` | Get single floorplandesk |
| `nexudus floorplandesks create --floor-plan-id <value> --name <value> --item-type <value> --size <value> --capacity <value> --price <value> --position-x <value> --position-y <value> --position-z <value> --agent` | Create floorplandesk |
| `nexudus floorplandesks update <id> --name "New Name" --agent` | Update floorplandesk |
| `nexudus floorplandesks delete <id> --yes --agent` | Delete floorplandesk (no prompt) |

#### FloorPlanDesk list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-id` | long | ID of the floor plan this unit belongs to |
| `--coworker-id` | long | ID of the customer assigned to this unit (used for dedicated desks and offices) |
| `--sensor-id` | long | ID of the IoT sensor monitoring occupancy or environmental conditions in this unit |
| `--name` | string | Display name of the floor plan unit (e.g. 'Office 3', 'Hot Desk 12') |
| `--item-type` | enum | Type of area this unit represents: Office, DedicatedDesk, HotDesk, Room, or Other |
| `--resource-id` | long | ID of the bookable resource linked to this unit, enabling customers to book it via the floor plan view |
| `--size` | decimal | Floor area of this unit (e.g. in sq ft or sq m, depending on the location's unit setting) |
| `--from-size` | range | |
| `--to-size` | range | |
| `--size-is-linked-to-area` | bool | When true, the Size value is automatically calculated from the drawn shape area on the floor plan canvas |
| `--capacity` | decimal | Number of people this unit can accommodate at the same time |
| `--from-capacity` | range | |
| `--to-capacity` | range | |
| `--price` | decimal | Indicative price displayed on the floor plan view (informational only; actual billing is handled by products and contracts) |
| `--from-price` | range | |
| `--to-price` | range | |
| `--area` | string | Computed area of the drawn shape on the floor plan canvas, set automatically by the editor |
| `--notes` | string | Internal notes about this unit, visible to admins only |
| `--available` | bool | Whether this unit is currently available for assignment or booking |
| `--available-to-ai` | bool | Whether this unit is available to any AI channels (Email, Chat or WhatsApp) for recommendations for private offices; |
| `--notes-for-ai` | string | Notes or instructions for AI channels to consider when recommending this unit for private offices (e.g. 'great natural light but a bit noisy') |
| `--show-price-for-ai` | bool | Whether to show the price of this unit in AI channel recommendations and responses based on users' budget preferences |
| `--price-for-ai` | decimal | Override price to show in AI channel recommendations and responses based on users' budget preferences (if not set, the regular Price value is used) |
| `--from-price-for-ai` | range | |
| `--to-price-for-ai` | range | |
| `--position-x` | int | X coordinate of this unit's position on the floor plan canvas |
| `--from-position-x` | range | |
| `--to-position-x` | range | |
| `--position-y` | int | Y coordinate of this unit's position on the floor plan canvas |
| `--from-position-y` | range | |
| `--to-position-y` | range | |
| `--position-z` | int | Z-index (draw order) of this unit on the floor plan canvas; higher values render on top |
| `--from-position-z` | range | |
| `--to-position-z` | range | |
| `--access-control-group-id` | string | Access control group identifier that governs door/entry access for this unit |
| `--tunnel-private-group-id` | string | Network tunnel group identifier for private network access scoped to this unit |
| `--coworker-contract-ids` | string | Comma-separated list of contract IDs currently assigned to this unit |
| `--coworker-contract-full-names` | string | Comma-separated list of customer names from contracts assigned to this unit |
| `--coworker-contract-start-dates` | string | Comma-separated list of start dates for contracts assigned to this unit |
| `--available-from-time` | DateTime | UTC date/time from which this unit becomes available |
| `--from-available-from-time` | range | |
| `--to-available-from-time` | range | |
| `--available-to-time` | DateTime | UTC date/time until which this unit is available |
| `--from-available-to-time` | range | |
| `--to-available-to-time` | range | |
| `--available-from-time-local` | DateTime | Local date/time from which this unit becomes available (derived from AvailableFromTime) |
| `--from-available-from-time-local` | range | |
| `--to-available-from-time-local` | range | |
| `--available-to-time-local` | DateTime | Local date/time until which this unit is available (derived from AvailableToTime) |
| `--from-available-to-time-local` | range | |
| `--to-available-to-time-local` | range | |
| `--archilogic-unique-id` | string | Unique identifier linking this unit to its corresponding element in an Archilogic 3D model |
| `--floor-plan-layout-asset-unique-id` | string | Unique identifier linking this unit to a component in the associated floor plan layout template |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanDesk sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlanDesk create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-id` | long, required | ID of the floor plan this unit belongs to |
| `--coworker-id` | long | ID of the customer assigned to this unit (used for dedicated desks and offices) |
| `--sensor-id` | long | ID of the IoT sensor monitoring occupancy or environmental conditions in this unit |
| `--name` | string, required | Display name of the floor plan unit (e.g. 'Office 3', 'Hot Desk 12') |
| `--item-type` | enum, required | Type of area this unit represents: Office, DedicatedDesk, HotDesk, Room, or Other |
| `--resource-id` | long | ID of the bookable resource linked to this unit, enabling customers to book it via the floor plan view |
| `--size` | decimal, required | Floor area of this unit (e.g. in sq ft or sq m, depending on the location's unit setting) |
| `--size-is-linked-to-area` | bool | When true, the Size value is automatically calculated from the drawn shape area on the floor plan canvas |
| `--capacity` | decimal, required | Number of people this unit can accommodate at the same time |
| `--price` | decimal, required | Indicative price displayed on the floor plan view (informational only; actual billing is handled by products and contracts) |
| `--area` | string | Computed area of the drawn shape on the floor plan canvas, set automatically by the editor |
| `--notes` | string | Internal notes about this unit, visible to admins only |
| `--available` | bool | Whether this unit is currently available for assignment or booking |
| `--available-to-ai` | bool | Whether this unit is available to any AI channels (Email, Chat or WhatsApp) for recommendations for private offices; |
| `--notes-for-ai` | string | Notes or instructions for AI channels to consider when recommending this unit for private offices (e.g. 'great natural light but a bit noisy') |
| `--show-price-for-ai` | bool | Whether to show the price of this unit in AI channel recommendations and responses based on users' budget preferences |
| `--price-for-ai` | decimal | Override price to show in AI channel recommendations and responses based on users' budget preferences (if not set, the regular Price value is used) |
| `--position-x` | int, required | X coordinate of this unit's position on the floor plan canvas |
| `--position-y` | int, required | Y coordinate of this unit's position on the floor plan canvas |
| `--position-z` | int, required | Z-index (draw order) of this unit on the floor plan canvas; higher values render on top |
| `--access-control-group-id` | string | Access control group identifier that governs door/entry access for this unit |
| `--tunnel-private-group-id` | string | Network tunnel group identifier for private network access scoped to this unit |
| `--coworker-contract-ids` | string | Comma-separated list of contract IDs currently assigned to this unit |
| `--coworker-contract-full-names` | string | Comma-separated list of customer names from contracts assigned to this unit |
| `--coworker-contract-start-dates` | string | Comma-separated list of start dates for contracts assigned to this unit |
| `--available-from-time` | DateTime | UTC date/time from which this unit becomes available |
| `--available-to-time` | DateTime | UTC date/time until which this unit is available |
| `--available-from-time-local` | DateTime | Local date/time from which this unit becomes available (derived from AvailableFromTime) |
| `--available-to-time-local` | DateTime | Local date/time until which this unit is available (derived from AvailableToTime) |
| `--archilogic-unique-id` | string | Unique identifier linking this unit to its corresponding element in an Archilogic 3D model |
| `--floor-plan-layout-asset-unique-id` | string | Unique identifier linking this unit to a component in the associated floor plan layout template |

#### FloorPlanDesk update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-id` | long | ID of the floor plan this unit belongs to |
| `--coworker-id` | long | ID of the customer assigned to this unit (used for dedicated desks and offices) |
| `--sensor-id` | long | ID of the IoT sensor monitoring occupancy or environmental conditions in this unit |
| `--name` | string | Display name of the floor plan unit (e.g. 'Office 3', 'Hot Desk 12') |
| `--item-type` | enum | Type of area this unit represents: Office, DedicatedDesk, HotDesk, Room, or Other |
| `--resource-id` | long | ID of the bookable resource linked to this unit, enabling customers to book it via the floor plan view |
| `--size` | decimal | Floor area of this unit (e.g. in sq ft or sq m, depending on the location's unit setting) |
| `--size-is-linked-to-area` | bool | When true, the Size value is automatically calculated from the drawn shape area on the floor plan canvas |
| `--capacity` | decimal | Number of people this unit can accommodate at the same time |
| `--price` | decimal | Indicative price displayed on the floor plan view (informational only; actual billing is handled by products and contracts) |
| `--area` | string | Computed area of the drawn shape on the floor plan canvas, set automatically by the editor |
| `--notes` | string | Internal notes about this unit, visible to admins only |
| `--available` | bool | Whether this unit is currently available for assignment or booking |
| `--available-to-ai` | bool | Whether this unit is available to any AI channels (Email, Chat or WhatsApp) for recommendations for private offices; |
| `--notes-for-ai` | string | Notes or instructions for AI channels to consider when recommending this unit for private offices (e.g. 'great natural light but a bit noisy') |
| `--show-price-for-ai` | bool | Whether to show the price of this unit in AI channel recommendations and responses based on users' budget preferences |
| `--price-for-ai` | decimal | Override price to show in AI channel recommendations and responses based on users' budget preferences (if not set, the regular Price value is used) |
| `--position-x` | int | X coordinate of this unit's position on the floor plan canvas |
| `--position-y` | int | Y coordinate of this unit's position on the floor plan canvas |
| `--position-z` | int | Z-index (draw order) of this unit on the floor plan canvas; higher values render on top |
| `--access-control-group-id` | string | Access control group identifier that governs door/entry access for this unit |
| `--tunnel-private-group-id` | string | Network tunnel group identifier for private network access scoped to this unit |
| `--coworker-contract-ids` | string | Comma-separated list of contract IDs currently assigned to this unit |
| `--coworker-contract-full-names` | string | Comma-separated list of customer names from contracts assigned to this unit |
| `--coworker-contract-start-dates` | string | Comma-separated list of start dates for contracts assigned to this unit |
| `--available-from-time` | DateTime | UTC date/time from which this unit becomes available |
| `--available-to-time` | DateTime | UTC date/time until which this unit is available |
| `--available-from-time-local` | DateTime | Local date/time from which this unit becomes available (derived from AvailableFromTime) |
| `--available-to-time-local` | DateTime | Local date/time until which this unit is available (derived from AvailableToTime) |
| `--archilogic-unique-id` | string | Unique identifier linking this unit to its corresponding element in an Archilogic 3D model |
| `--floor-plan-layout-asset-unique-id` | string | Unique identifier linking this unit to a component in the associated floor plan layout template |

#### FloorPlanDesk PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--coworker-contract-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus floorplandesks update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### FloorPlanDesk (key fields)

`Id`, `FloorPlanName`, `CoworkerFullName`, `SensorName`, `Name`, `ResourceName`

#### FloorPlanDesk enum values

| Option | Valid values |
| ------ | ------------ |
| `--item-type` | `1` Office, `2` DedicatedDesk, `3` HotDesk, `4` Other, `5` Room |

<!-- END:GENERATED entity=FloorPlanDesks -->
