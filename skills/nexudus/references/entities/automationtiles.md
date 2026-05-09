# AutomationTiles

<!-- BEGIN:GENERATED entity=AutomationTiles -->

An **AutomationTile** represents a physical NFC chip and QR code tile that triggers actions in a Nexudus-powered coworking space. Each tile is linked to a single action (e.g. check-in, booking, door unlock, HTTP request) that fires when a customer scans or taps the tile.

The `Action` field determines what happens when the tile is scanned. Some actions require additional data in `ActionParameters`:

| Action | ActionParameters format |
| --- | --- |
| CheckIn / CheckOut / EventCheckIn | Not required |
| BookingCheckIn / ResourceCleaned / ShowNewBookingForm | Resource ID |
| BookResource | Resource ID `\|` default booking length in minutes (default 60) |
| BookDesk | Desk (floor plan item) ID `\|` default booking length in minutes (default 480) |
| ExtendBookingBy | Number of minutes to extend |
| RequestUrl | Target URL for the HTTP POST request |
| RedirectUrl | URL to redirect the user to |
| UnlockAct365Door / UnlockDoorDeckDoor / UnlockKisiDoor | Door ID from the access-control provider |
| SmartLock | Smartalock locker bank ID |

Tiles can optionally be geo-fenced to restrict scanning to a physical area around the tile's installed location. Enable `EnableGeofence`, set `Latitude`/`Longitude`, and choose a `GeofencePrecission` level. `MaxDistanceMeters` overrides the precision preset with a custom radius.

Set `CheckCustomerIn` to also check the customer into the space when they scan the tile, regardless of the tile's primary action.

AutomationTiles support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus automationtiles list --agent` | List all automationtiles |
| `nexudus automationtiles list --id <id> --agent` | Filter by single ID |
| `nexudus automationtiles list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus automationtiles list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus automationtiles list --name <value> --action <value> --agent` | Filter automationtiles by properties |
| `nexudus automationtiles list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus automationtiles get <id> --agent` | Get single automationtile |
| `nexudus automationtiles create --business-id <value> --name <value> --action <value> --geofence-precission <value> --agent` | Create automationtile |
| `nexudus automationtiles update <id> --name "New Name" --agent` | Update automationtile |
| `nexudus automationtiles delete <id> --yes --agent` | Delete automationtile (no prompt) |

#### AutomationTile list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Tile name used to identify it in the admin panel |
| `--tile-number` | string | Unique tile identifier (GUID) auto-assigned on creation. Used to generate the QR code and NFC URL |
| `--action` | enum | Action triggered when the tile is scanned: None, CheckIn, CheckOut, BookingCheckIn, EventCheckIn, ExtendBookingBy, RequestUrl, RedirectUrl, ResourceCleaned, BookResource, BookDesk, ShowNewBookingForm, UnlockAct365Door, UnlockDoorDeckDoor, UnlockKisiDoor, SmartLock, etc. |
| `--action-parameters` | string | Parameters for the selected action. Format depends on the action type — e.g. a resource ID, a URL, or a resource ID|duration pair |
| `--enable-geofence` | bool | Whether to restrict the tile to a geographic area. When enabled, the tile only works if the user is within the configured radius of the tile's coordinates |
| `--check-customer-in` | bool | Whether to also check the customer into the space when they scan the tile, regardless of the primary action |
| `--longitude` | decimal | Longitude of the tile's installed location. Used for geofencing |
| `--from-longitude` | range | |
| `--to-longitude` | range | |
| `--latitude` | decimal | Latitude of the tile's installed location. Used for geofencing |
| `--from-latitude` | range | |
| `--to-latitude` | range | |
| `--geofence-precission` | enum | Geofence precision level: Low, Medium, High, or VeryHigh. Higher precision requires the user to be closer to the tile coordinates |
| `--max-distance-meters` | int | Custom maximum distance in meters from the tile's coordinates. Overrides the precision preset when set |
| `--from-max-distance-meters` | range | |
| `--to-max-distance-meters` | range | |
| `--success-message` | string | Custom message shown to the user when the tile action completes successfully |
| `--error-message` | string | Custom error message shown to the user when the tile action fails |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AutomationTile create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required |  |
| `--name` | string, required | Tile name used to identify it in the admin panel |
| `--tile-number` | string | Unique tile identifier (GUID) auto-assigned on creation. Used to generate the QR code and NFC URL |
| `--action` | enum, required | Action triggered when the tile is scanned: None, CheckIn, CheckOut, BookingCheckIn, EventCheckIn, ExtendBookingBy, RequestUrl, RedirectUrl, ResourceCleaned, BookResource, BookDesk, ShowNewBookingForm, UnlockAct365Door, UnlockDoorDeckDoor, UnlockKisiDoor, SmartLock, etc. |
| `--action-parameters` | string | Parameters for the selected action. Format depends on the action type — e.g. a resource ID, a URL, or a resource ID|duration pair |
| `--enable-geofence` | bool | Whether to restrict the tile to a geographic area. When enabled, the tile only works if the user is within the configured radius of the tile's coordinates |
| `--check-customer-in` | bool | Whether to also check the customer into the space when they scan the tile, regardless of the primary action |
| `--longitude` | decimal | Longitude of the tile's installed location. Used for geofencing |
| `--latitude` | decimal | Latitude of the tile's installed location. Used for geofencing |
| `--geofence-precission` | enum, required | Geofence precision level: Low, Medium, High, or VeryHigh. Higher precision requires the user to be closer to the tile coordinates |
| `--max-distance-meters` | int | Custom maximum distance in meters from the tile's coordinates. Overrides the precision preset when set |
| `--success-message` | string | Custom message shown to the user when the tile action completes successfully |
| `--error-message` | string | Custom error message shown to the user when the tile action fails |
| `--resources` | list, repeat flag |  |
| `--added-resources` | list, repeat flag |  |
| `--removed-resources` | list, repeat flag |  |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--time-passes` | list, repeat flag |  |
| `--added-time-passes` | list, repeat flag |  |
| `--removed-time-passes` | list, repeat flag |  |
| `--floor-plan-desks` | list, repeat flag |  |
| `--added-floor-plan-desks` | list, repeat flag |  |
| `--removed-floor-plan-desks` | list, repeat flag |  |

#### AutomationTile update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long |  |
| `--name` | string | Tile name used to identify it in the admin panel |
| `--tile-number` | string | Unique tile identifier (GUID) auto-assigned on creation. Used to generate the QR code and NFC URL |
| `--action` | enum | Action triggered when the tile is scanned: None, CheckIn, CheckOut, BookingCheckIn, EventCheckIn, ExtendBookingBy, RequestUrl, RedirectUrl, ResourceCleaned, BookResource, BookDesk, ShowNewBookingForm, UnlockAct365Door, UnlockDoorDeckDoor, UnlockKisiDoor, SmartLock, etc. |
| `--action-parameters` | string | Parameters for the selected action. Format depends on the action type — e.g. a resource ID, a URL, or a resource ID|duration pair |
| `--enable-geofence` | bool | Whether to restrict the tile to a geographic area. When enabled, the tile only works if the user is within the configured radius of the tile's coordinates |
| `--check-customer-in` | bool | Whether to also check the customer into the space when they scan the tile, regardless of the primary action |
| `--longitude` | decimal | Longitude of the tile's installed location. Used for geofencing |
| `--latitude` | decimal | Latitude of the tile's installed location. Used for geofencing |
| `--geofence-precission` | enum | Geofence precision level: Low, Medium, High, or VeryHigh. Higher precision requires the user to be closer to the tile coordinates |
| `--max-distance-meters` | int | Custom maximum distance in meters from the tile's coordinates. Overrides the precision preset when set |
| `--success-message` | string | Custom message shown to the user when the tile action completes successfully |
| `--error-message` | string | Custom error message shown to the user when the tile action fails |
| `--resources` | list, repeat flag |  |
| `--added-resources` | list, repeat flag |  |
| `--removed-resources` | list, repeat flag |  |
| `--tariffs` | list, repeat flag |  |
| `--added-tariffs` | list, repeat flag |  |
| `--removed-tariffs` | list, repeat flag |  |
| `--time-passes` | list, repeat flag |  |
| `--added-time-passes` | list, repeat flag |  |
| `--removed-time-passes` | list, repeat flag |  |
| `--floor-plan-desks` | list, repeat flag |  |
| `--added-floor-plan-desks` | list, repeat flag |  |
| `--removed-floor-plan-desks` | list, repeat flag |  |

### AutomationTile (key fields)

`Id`, `Name`, `Action`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `TimePasses`, `AddedTimePasses`, `RemovedTimePasses`, `FloorPlanDesks`, `AddedFloorPlanDesks`, `RemovedFloorPlanDesks`

#### AutomationTile enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` UnlockAct365Door, `3` CheckIn, `4` CheckOut, `5` BookingCheckIn, `6` EventCheckIn, `7` ResourceCleaned, `8` RequestUrl, `9` RedirectUrl, `10` UnlockDoorDeckDoor, `11` UnlockKisiDoor, `12` BookResource, `13` BookDesk, `14` ShowNewBookingForm, `15` SmartLock, `16` ExtendBookingBy, `17` ShowAcsModal, `18` UnlockPadWordDoor, `19` UnlockOPaxtonNet2Door |
| `--geofence-precission` | `1` Low, `2` Medium, `3` High, `4` VeryHigh |

<!-- END:GENERATED entity=AutomationTiles -->
