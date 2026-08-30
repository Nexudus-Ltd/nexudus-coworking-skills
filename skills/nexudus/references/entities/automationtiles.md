# AutomationTiles

<!-- BEGIN:GENERATED entity=AutomationTiles -->

An automation tile is a physical NFC or QR-code tile at a location that runs a configured action when a customer scans it, optionally restricting use by bookings, plans, passes, desks or offices, and geofencing.

AutomationTiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus automationtiles list --agent` | List all automationtiles |
| `nexudus automationtiles list --id <id> --agent` | Filter by single ID |
| `nexudus automationtiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus automationtiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus automationtiles list --name <value> --action <value> --agent` | Filter automationtiles by properties |
| `nexudus automationtiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus automationtiles list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus automationtiles get <id> --agent` | Get single automationtile |
| `nexudus automationtiles create --business-id <value> --name <value> --action <value> --geofence-precission <value> --agent` | Create automationtile |
| `nexudus automationtiles update <id> --name "New Name" --agent` | Update automationtile |
| `nexudus automationtiles delete <id> --yes --agent` | Delete automationtile (no prompt) |

#### AutomationTile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this automation tile. |
| `--name` | string | Name shown to customers when they scan the tile. |
| `--tile-number` | string | Unique GUID assigned automatically when the tile is created; it identifies the tile in its QR-code and scan URL. |
| `--action` | enum | Action performed when a customer scans the tile: None disables it; values also support check-in/out, booking and event actions, resource cleaning, HTTPS requests or redirects, and configured access-control or locker systems. |
| `--action-parameters` | string | Action-specific value: use a resource or desk ID, optionally followed by | and booking duration in minutes; a resource ID optionally followed by | and desk ID for booking check-in or the booking form; minutes for ExtendBookingBy; or the relevant door, locker, or URL ID. RequestUrl must start with https. |
| `--enable-geofence` | bool | Whether tile use is restricted to the geographic area configured by its coordinates and radius or precision. |
| `--check-customer-in` | bool | Whether to check the customer in at the tile's location before running a non-CheckIn or non-CheckOut action. |
| `--longitude` | decimal | Longitude coordinate of the tile for geographic restriction when EnableGeofence is enabled. |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | Latitude coordinate of the tile for geographic restriction when EnableGeofence is enabled. |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--geofence-precission` | enum | Geofence precision setting: Low, Medium, High, or VeryHigh; use with the tile coordinates when EnableGeofence is enabled. |
| `--max-distance-meters` | int | Optional geofence radius in meters from the tile coordinates; use it when EnableGeofence is enabled. |
| `--from-max-distance-meters` | range | |
| `--to-max-distance-meters` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AutomationTile sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AutomationTile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this automation tile. |
| `--name` | string, required | Name shown to customers when they scan the tile. |
| `--action` | enum, required | Action performed when a customer scans the tile: None disables it; values also support check-in/out, booking and event actions, resource cleaning, HTTPS requests or redirects, and configured access-control or locker systems. |
| `--action-parameters` | string | Action-specific value: use a resource or desk ID, optionally followed by | and booking duration in minutes; a resource ID optionally followed by | and desk ID for booking check-in or the booking form; minutes for ExtendBookingBy; or the relevant door, locker, or URL ID. RequestUrl must start with https. |
| `--enable-geofence` | bool | Whether tile use is restricted to the geographic area configured by its coordinates and radius or precision. |
| `--check-customer-in` | bool | Whether to check the customer in at the tile's location before running a non-CheckIn or non-CheckOut action. |
| `--longitude` | decimal | Longitude coordinate of the tile for geographic restriction when EnableGeofence is enabled. |
| `--latitude` | decimal | Latitude coordinate of the tile for geographic restriction when EnableGeofence is enabled. |
| `--geofence-precission` | enum, required | Geofence precision setting: Low, Medium, High, or VeryHigh; use with the tile coordinates when EnableGeofence is enabled. |
| `--max-distance-meters` | int | Optional geofence radius in meters from the tile coordinates; use it when EnableGeofence is enabled. |
| `--resources` | list, repeat flag | List of resources for which the customer must have a current booking to use this tile; an empty list imposes no resource-booking restriction. |
| `--added-resources` | list, repeat flag | The added resources value for this automation tile |
| `--removed-resources` | list, repeat flag | The removed resources value for this automation tile |
| `--tariffs` | list, repeat flag | List of plans the customer must hold through an active contract to use this tile; an empty list imposes no plan restriction. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this automation tile |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this automation tile |
| `--time-passes` | list, repeat flag | List of passes the customer must hold to use this tile; an empty list imposes no pass restriction. |
| `--added-time-passes` | list, repeat flag | The added time passes value for this automation tile |
| `--removed-time-passes` | list, repeat flag | The removed time passes value for this automation tile |
| `--floor-plan-desks` | list, repeat flag | List of desks or offices the customer or their paying member must hold through an active contract to use this tile; an empty list imposes no desk restriction. |
| `--added-floor-plan-desks` | list, repeat flag | The added floor plan desks value for this automation tile |
| `--removed-floor-plan-desks` | list, repeat flag | The removed floor plan desks value for this automation tile |

#### AutomationTile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this automation tile. |
| `--name` | string | Name shown to customers when they scan the tile. |
| `--action` | enum | Action performed when a customer scans the tile: None disables it; values also support check-in/out, booking and event actions, resource cleaning, HTTPS requests or redirects, and configured access-control or locker systems. |
| `--action-parameters` | string | Action-specific value: use a resource or desk ID, optionally followed by | and booking duration in minutes; a resource ID optionally followed by | and desk ID for booking check-in or the booking form; minutes for ExtendBookingBy; or the relevant door, locker, or URL ID. RequestUrl must start with https. |
| `--enable-geofence` | bool | Whether tile use is restricted to the geographic area configured by its coordinates and radius or precision. |
| `--check-customer-in` | bool | Whether to check the customer in at the tile's location before running a non-CheckIn or non-CheckOut action. |
| `--longitude` | decimal | Longitude coordinate of the tile for geographic restriction when EnableGeofence is enabled. |
| `--latitude` | decimal | Latitude coordinate of the tile for geographic restriction when EnableGeofence is enabled. |
| `--geofence-precission` | enum | Geofence precision setting: Low, Medium, High, or VeryHigh; use with the tile coordinates when EnableGeofence is enabled. |
| `--max-distance-meters` | int | Optional geofence radius in meters from the tile coordinates; use it when EnableGeofence is enabled. |
| `--resources` | list, repeat flag | List of resources for which the customer must have a current booking to use this tile; an empty list imposes no resource-booking restriction. |
| `--added-resources` | list, repeat flag | The added resources value for this automation tile |
| `--removed-resources` | list, repeat flag | The removed resources value for this automation tile |
| `--tariffs` | list, repeat flag | List of plans the customer must hold through an active contract to use this tile; an empty list imposes no plan restriction. |
| `--added-tariffs` | list, repeat flag | The added tariffs value for this automation tile |
| `--removed-tariffs` | list, repeat flag | The removed tariffs value for this automation tile |
| `--time-passes` | list, repeat flag | List of passes the customer must hold to use this tile; an empty list imposes no pass restriction. |
| `--added-time-passes` | list, repeat flag | The added time passes value for this automation tile |
| `--removed-time-passes` | list, repeat flag | The removed time passes value for this automation tile |
| `--floor-plan-desks` | list, repeat flag | List of desks or offices the customer or their paying member must hold through an active contract to use this tile; an empty list imposes no desk restriction. |
| `--added-floor-plan-desks` | list, repeat flag | The added floor plan desks value for this automation tile |
| `--removed-floor-plan-desks` | list, repeat flag | The removed floor plan desks value for this automation tile |

### AutomationTile (key fields)

`Id`, `Name`, `Action`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `TimePasses`, `AddedTimePasses`, `RemovedTimePasses`, `FloorPlanDesks`, `AddedFloorPlanDesks`, `RemovedFloorPlanDesks`

#### AutomationTile enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` UnlockAct365Door, `3` CheckIn, `4` CheckOut, `5` BookingCheckIn, `6` EventCheckIn, `7` ResourceCleaned, `8` RequestUrl, `9` RedirectUrl, `10` UnlockDoorDeckDoor, `11` UnlockKisiDoor, `12` BookResource, `13` BookDesk, `14` ShowNewBookingForm, `15` SmartLock, `16` ExtendBookingBy, `17` ShowAcsModal, `18` UnlockPadWordDoor, `19` UnlockOPaxtonNet2Door |
| `--geofence-precission` | `1` Low, `2` Medium, `3` High, `4` VeryHigh |

<!-- END:GENERATED entity=AutomationTiles -->
