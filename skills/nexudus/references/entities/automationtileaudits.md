# AutomationTileAudits

<!-- BEGIN:GENERATED entity=AutomationTileAudits -->

An automation tile audit is a system-generated, read-only record of a customer scan at a location, including the configured action, outcome, customer identity, and result message.

AutomationTileAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus automationtileaudits list --agent` | List all automationtileaudits |
| `nexudus automationtileaudits list --id <id> --agent` | Filter by single ID |
| `nexudus automationtileaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus automationtileaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus automationtileaudits list --description <value> --action <value> --agent` | Filter automationtileaudits by properties |
| `nexudus automationtileaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus automationtileaudits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus automationtileaudits get <id> --agent` | Get single automationtileaudit |
| `nexudus automationtileaudits create --automation-tile-id <value> --description <value> --action <value> --tile-audit-type <value> --agent` | Create automationtileaudit |
| `nexudus automationtileaudits update <id> --name "New Name" --agent` | Update automationtileaudit |
| `nexudus automationtileaudits delete <id> --yes --agent` | Delete automationtileaudit (no prompt) |

#### AutomationTileAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--automation-tile-id` | long | ID of the automation tile that was scanned and whose location determines access to this audit entry. |
| `--automation-tile-name` | string |  |
| `--description` | string | Required system-generated message describing the result of the tile scan. |
| `--action-by` | string | System-generated customer identity in the format FullName (Email) #CustomerId for the person who scanned the tile. |
| `--action` | enum | System-generated action configured on the scanned tile, recorded when the scan is processed. |
| `--tile-audit-type` | enum | System-generated outcome of the scan: Success when the action completed, or Failure when processing was rejected or failed. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### AutomationTileAudit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### AutomationTileAudit create options

| Option | Type | Description |
| --- | --- | --- |
| `--automation-tile-id` | long, required | ID of the automation tile that was scanned and whose location determines access to this audit entry. |
| `--description` | string, required | Required system-generated message describing the result of the tile scan. |
| `--action-by` | string | System-generated customer identity in the format FullName (Email) #CustomerId for the person who scanned the tile. |
| `--action` | enum, required | System-generated action configured on the scanned tile, recorded when the scan is processed. |
| `--tile-audit-type` | enum, required | System-generated outcome of the scan: Success when the action completed, or Failure when processing was rejected or failed. |

#### AutomationTileAudit update options

| Option | Type | Description |
| --- | --- | --- |
| `--automation-tile-id` | long | ID of the automation tile that was scanned and whose location determines access to this audit entry. |
| `--description` | string | Required system-generated message describing the result of the tile scan. |
| `--action-by` | string | System-generated customer identity in the format FullName (Email) #CustomerId for the person who scanned the tile. |
| `--action` | enum | System-generated action configured on the scanned tile, recorded when the scan is processed. |
| `--tile-audit-type` | enum | System-generated outcome of the scan: Success when the action completed, or Failure when processing was rejected or failed. |

### AutomationTileAudit (key fields)

`Id`, `Description`, `Action`, `TileAuditType`

#### AutomationTileAudit enum values

| Option | Valid values |
| ------ | ------------ |
| `--action` | `1` None, `2` UnlockAct365Door, `3` CheckIn, `4` CheckOut, `5` BookingCheckIn, `6` EventCheckIn, `7` ResourceCleaned, `8` RequestUrl, `9` RedirectUrl, `10` UnlockDoorDeckDoor, `11` UnlockKisiDoor, `12` BookResource, `13` BookDesk, `14` ShowNewBookingForm, `15` SmartLock, `16` ExtendBookingBy, `17` ShowAcsModal, `18` UnlockPadWordDoor, `19` UnlockOPaxtonNet2Door |
| `--tile-audit-type` | `1` Success, `2` Failure |

<!-- END:GENERATED entity=AutomationTileAudits -->
