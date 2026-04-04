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
| `nexudus inventoryassets list --id <id> --agent` | Filter by single ID |
| `nexudus inventoryassets list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus inventoryassets list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus inventoryassets list --name <value> --agent` | Filter inventoryassets by properties |
| `nexudus inventoryassets list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus inventoryassets get <id> --agent` | Get single inventoryasset |
| `nexudus inventoryassets create --business-id <value> --name <value> --agent` | Create inventoryasset |
| `nexudus inventoryassets update <id> --name "New Name" --agent` | Update inventoryasset |
| `nexudus inventoryassets delete <id> --yes --agent` | Delete inventoryasset (no prompt) |
| `nexudus inventoryassets run-command <key> <ids> --agent` | Run entity command |

#### InventoryAsset list filter options

`--business-id`, `--name`, `--description`, `--sku`, `--new-image-url`, `--clear-image-file`, `--value`, `--floor-plan-desk-id`, `--resource-id`, `--assign-to-type`

#### InventoryAsset create options

`--business-id` (required), `--name` (required), `--description`, `--sku`, `--new-image-url`, `--clear-image-file`, `--value`, `--floor-plan-desk-id`, `--assigned-coworkers` (list, repeat flag), `--added-assigned-coworkers` (list, repeat flag), `--removed-assigned-coworkers` (list, repeat flag), `--resource-id`, `--assign-to-type`

#### InventoryAsset update options

`--business-id`, `--name`, `--description`, `--sku`, `--new-image-url`, `--clear-image-file`, `--value`, `--floor-plan-desk-id`, `--assigned-coworkers` (list, repeat flag), `--added-assigned-coworkers` (list, repeat flag), `--removed-assigned-coworkers` (list, repeat flag), `--resource-id`, `--assign-to-type`

### InventoryAsset (key fields)

`Id`, `BusinessName`, `Name`

**List properties (only returned by `get`, not by `list`):** `AssignedCoworkers`, `AddedAssignedCoworkers`, `RemovedAssignedCoworkers`

#### InventoryAsset enum values

| Option | Valid values |
| ------ | ------------ |
| `--assign-to-type` | `1` Location, `2` Resource, `3` FloorPlanItem |

<!-- END:GENERATED entity=InventoryAssets -->
