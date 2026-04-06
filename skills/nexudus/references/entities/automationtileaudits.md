# AutomationTileAudits

<!-- BEGIN:GENERATED entity=AutomationTileAudits -->

An **AutomationTileAudit** is a log entry recorded each time an `AutomationTile` is scanned or tapped. It captures the outcome (success or failure), the action that was triggered, and the identity of the user who scanned the tile.

Use this entity to review tile usage history, troubleshoot scanning failures, and track which customers are interacting with specific tiles.

AutomationTileAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus automationtileaudits list --agent` | List all automationtileaudits |
| `nexudus automationtileaudits list --id <id> --agent` | Filter by single ID |
| `nexudus automationtileaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus automationtileaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus automationtileaudits list --description <value> --action <value> --agent` | Filter automationtileaudits by properties |
| `nexudus automationtileaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus automationtileaudits get <id> --agent` | Get single automationtileaudit |
| `nexudus automationtileaudits create --automation-tile-id <value> --description <value> --action <value> --tile-audit-type <value> --agent` | Create automationtileaudit |
| `nexudus automationtileaudits update <id> --name "New Name" --agent` | Update automationtileaudit |
| `nexudus automationtileaudits delete <id> --yes --agent` | Delete automationtileaudit (no prompt) |

#### AutomationTileAudit list filter options

`--automation-tile-id`, `--description`, `--action-by`, `--action`, `--tile-audit-type`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### AutomationTileAudit create options

`--automation-tile-id` (required), `--description` (required), `--action-by`, `--action` (required), `--tile-audit-type` (required)

#### AutomationTileAudit update options

`--automation-tile-id`, `--description`, `--action-by`, `--action`, `--tile-audit-type`

### AutomationTileAudit (key fields)

`Id`, `Description`, `Action`, `TileAuditType`

#### AutomationTileAudit enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` UnlockAct365Door, `3` CheckIn, `4` CheckOut, `5` BookingCheckIn, `6` EventCheckIn, `7` ResourceCleaned, `8` RequestUrl, `9` RedirectUrl, `10` UnlockDoorDeckDoor, `11` UnlockKisiDoor, `12` BookResource, `13` BookDesk, `14` ShowNewBookingForm, `15` SmartLock, `16` ExtendBookingBy, `17` ShowAcsModal, `18` UnlockPadWordDoor, `19` UnlockOPaxtonNet2Door |
| `--tile-audit-type` | `1` Success, `2` Failure |

<!-- END:GENERATED entity=AutomationTileAudits -->
