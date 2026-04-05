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
| `nexudus automationtiles create --business-id <value> --name <value> --agent` | Create automationtile |
| `nexudus automationtiles update <id> --name "New Name" --agent` | Update automationtile |
| `nexudus automationtiles delete <id> --yes --agent` | Delete automationtile (no prompt) |

#### AutomationTile list filter options

`--business-id`, `--name`, `--tile-number`, `--action`, `--action-parameters`, `--enable-geofence`, `--check-customer-in`, `--longitude`, `--from-longitude` (range), `--to-longitude` (range), `--latitude`, `--from-latitude` (range), `--to-latitude` (range), `--geofence-precission`, `--max-distance-meters`, `--from-max-distance-meters` (range), `--to-max-distance-meters` (range), `--success-message`, `--error-message`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### AutomationTile create options

`--business-id` (required), `--name` (required), `--tile-number`, `--action`, `--action-parameters`, `--enable-geofence`, `--check-customer-in`, `--longitude`, `--latitude`, `--geofence-precission`, `--max-distance-meters`, `--success-message`, `--error-message`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--time-passes` (list, repeat flag), `--added-time-passes` (list, repeat flag), `--removed-time-passes` (list, repeat flag), `--floor-plan-desks` (list, repeat flag), `--added-floor-plan-desks` (list, repeat flag), `--removed-floor-plan-desks` (list, repeat flag)

#### AutomationTile update options

`--business-id`, `--name`, `--tile-number`, `--action`, `--action-parameters`, `--enable-geofence`, `--check-customer-in`, `--longitude`, `--latitude`, `--geofence-precission`, `--max-distance-meters`, `--success-message`, `--error-message`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag), `--tariffs` (list, repeat flag), `--added-tariffs` (list, repeat flag), `--removed-tariffs` (list, repeat flag), `--time-passes` (list, repeat flag), `--added-time-passes` (list, repeat flag), `--removed-time-passes` (list, repeat flag), `--floor-plan-desks` (list, repeat flag), `--added-floor-plan-desks` (list, repeat flag), `--removed-floor-plan-desks` (list, repeat flag)

### AutomationTile (key fields)

`Id`, `Name`, `Action`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`, `Tariffs`, `AddedTariffs`, `RemovedTariffs`, `TimePasses`, `AddedTimePasses`, `RemovedTimePasses`, `FloorPlanDesks`, `AddedFloorPlanDesks`, `RemovedFloorPlanDesks`

#### AutomationTile enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` UnlockAct365Door, `3` CheckIn, `4` CheckOut, `5` BookingCheckIn, `6` EventCheckIn, `7` ResourceCleaned, `8` RequestUrl, `9` RedirectUrl, `10` UnlockDoorDeckDoor, `11` UnlockKisiDoor, `12` BookResource, `13` BookDesk, `14` ShowNewBookingForm, `15` SmartLock, `16` ExtendBookingBy, `17` ShowAcsModal, `18` UnlockPadWordDoor, `19` UnlockOPaxtonNet2Door |
| `--geofence-precission` | `1` Low, `2` Medium, `3` High, `4` VeryHigh |

<!-- END:GENERATED entity=AutomationTiles -->
