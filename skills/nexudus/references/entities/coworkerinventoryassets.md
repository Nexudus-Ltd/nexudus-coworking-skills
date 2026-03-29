# CoworkerInventoryAssets

<!-- BEGIN:GENERATED entity=CoworkerInventoryAssets -->

CoworkerInventoryAssets support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkerinventoryassets list --agent` | List all coworkerinventoryassets |
| `nexudus coworkerinventoryassets list --query "search" --agent` | Search coworkerinventoryassets by name |
| `nexudus coworkerinventoryassets list --page 2 --size 10 --agent` | Paginated list |
| `nexudus coworkerinventoryassets get <id> --agent` | Get single coworkerinventoryasset |
| `nexudus coworkerinventoryassets create --coworker-id <value> --business <value> --inventory-asset-id <value> --assigned-from <value> --agent` | Create coworkerinventoryasset |
| `nexudus coworkerinventoryassets update <id> --name "New Name" --agent` | Update coworkerinventoryasset |
| `nexudus coworkerinventoryassets delete <id> --yes --agent` | Delete coworkerinventoryasset (no prompt) |

#### CoworkerInventoryAsset create options

`--coworker-id` (required), `--business` (required), `--inventory-asset-id` (required), `--notes`, `--assigned-from` (required), `--assigned-to`

#### CoworkerInventoryAsset update options

`--coworker-id`, `--inventory-asset-id`, `--notes`, `--assigned-from`, `--assigned-to`

### CoworkerInventoryAsset (key fields)

`Id`, `CoworkerId`, `CoworkerFullName`, `BusinessId`, `InventoryAssetId`, `InventoryAssetName`

<!-- END:GENERATED entity=CoworkerInventoryAssets -->
