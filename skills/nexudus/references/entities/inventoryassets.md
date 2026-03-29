# InventoryAssets

<!-- BEGIN:GENERATED entity=InventoryAssets -->

An **InventoryAsset** represents a physical asset — such as a desk, chair, monitor, printer, or other piece of equipment — that a location can track and optionally assign to customers.

Each asset belongs to a single location (`BusinessId`) and can be assigned to a specific scope via `AssignToType`:

| AssignToType value | Meaning |
| ------------------ | ------- |
| 1 (Location)       | Assigned to the location generally, not tied to a specific resource or floor-plan item |
| 2 (Resource)       | Linked to a bookable resource (e.g. a specific meeting room) via `ResourceId` |
| 3 (FloorPlanItem)  | Linked to a floor-plan desk via `FloorPlanDeskId` |

Assets may also be assigned to one or more coworkers. The read-only fields `CoworkerIds`, `CoworkerFullNames`, `CoworkerStartDates`, and `CoworkerEndDates` reflect current assignments. To manage coworker-level assignments, use the `CoworkerInventoryAsset` entity instead.

InventoryAssets support Search, Get, Create, Update, Delete.
InventoryAssets also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus inventoryassets list --agent` | List all inventoryassets |
| `nexudus inventoryassets list --query "search" --agent` | Search inventoryassets by name |
| `nexudus inventoryassets list --page 2 --size 10 --agent` | Paginated list |
| `nexudus inventoryassets get <id> --agent` | Get single inventoryasset |
| `nexudus inventoryassets create --business <value> --name <value> --agent` | Create inventoryasset |
| `nexudus inventoryassets update <id> --name "New Name" --agent` | Update inventoryasset |
| `nexudus inventoryassets delete <id> --yes --agent` | Delete inventoryasset (no prompt) |
| `nexudus inventoryassets run-command <key> <ids> --agent` | Run entity command |

#### InventoryAsset create options

`--business` (required), `--name` (required), `--description`, `--sku`, `--value`, `--floor-plan-desk-id`, `--resource-id`, `--assign-to-type`, `--new-image-url`, `--clear-image-file`

#### InventoryAsset update options

`--name`, `--description`, `--sku`, `--value`, `--floor-plan-desk-id`, `--resource-id`, `--assign-to-type`, `--new-image-url`, `--clear-image-file`

### InventoryAsset (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`

#### InventoryAsset enum values

| Option | Valid values |
| ------ | ------------ |
| `--assign-to-type` | `1` Location, `2` Resource, `3` FloorPlanItem |

<!-- END:GENERATED entity=InventoryAssets -->
