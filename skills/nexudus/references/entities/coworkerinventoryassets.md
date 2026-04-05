# CoworkerInventoryAssets

<!-- BEGIN:GENERATED entity=CoworkerInventoryAssets -->

A **CoworkerInventoryAsset** tracks inventory assets — such as chairs, desks, monitors, or other physical items — that have been assigned to a customer.

Each record links a `Coworker` to an `InventoryAsset` at a specific `Business` (location), with an assignment period defined by `AssignedFrom` and optionally `AssignedTo`. If `AssignedTo` is null, the asset is still assigned to the customer.

Read-only fields prefixed with `Coworker*` and `InventoryAsset*` are denormalized from the linked coworker and inventory asset records for convenience when listing or filtering.

CoworkerInventoryAssets support Search, Get, Create, Update, Delete.
CoworkerInventoryAssets also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus coworkerinventoryassets list --agent` | List all coworkerinventoryassets |
| `nexudus coworkerinventoryassets list --id <id> --agent` | Filter by single ID |
| `nexudus coworkerinventoryassets list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkerinventoryassets list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkerinventoryassets list --coworker-id <value> --business-id <value> --agent` | Filter coworkerinventoryassets by properties |
| `nexudus coworkerinventoryassets list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkerinventoryassets get <id> --agent` | Get single coworkerinventoryasset |
| `nexudus coworkerinventoryassets create --coworker-id <value> --business-id <value> --inventory-asset-id <value> --assigned-from <value> --agent` | Create coworkerinventoryasset |
| `nexudus coworkerinventoryassets update <id> --name "New Name" --agent` | Update coworkerinventoryasset |
| `nexudus coworkerinventoryassets delete <id> --yes --agent` | Delete coworkerinventoryasset (no prompt) |
| `nexudus coworkerinventoryassets run-command <key> <ids> --agent` | Run entity command |

#### CoworkerInventoryAsset list filter options

`--coworker-id`, `--business-id`, `--inventory-asset-id`, `--notes`, `--assigned-from`, `--from-assigned-from` (range), `--to-assigned-from` (range), `--assigned-to`, `--from-assigned-to` (range), `--to-assigned-to` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerInventoryAsset create options

`--coworker-id` (required), `--business-id` (required), `--inventory-asset-id` (required), `--notes`, `--assigned-from` (required), `--assigned-to`

#### CoworkerInventoryAsset update options

`--coworker-id`, `--business-id`, `--inventory-asset-id`, `--notes`, `--assigned-from`, `--assigned-to`

### CoworkerInventoryAsset (key fields)

`Id`, `CoworkerFullName`, `InventoryAssetName`

<!-- END:GENERATED entity=CoworkerInventoryAssets -->
