# InventoryAssets

<!-- BEGIN:GENERATED entity=InventoryAssets -->

InventoryAssets support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus inventoryassets list --agent` | List all inventoryassets |
| `nexudus inventoryassets list --query "search" --agent` | Search inventoryassets by name |
| `nexudus inventoryassets list --page 2 --size 10 --agent` | Paginated list |
| `nexudus inventoryassets get <id> --agent` | Get single inventoryasset |
| `nexudus inventoryassets create --business <value> --name <value> --agent` | Create inventoryasset |
| `nexudus inventoryassets update <id> --name "New Name" --agent` | Update inventoryasset |
| `nexudus inventoryassets delete <id> --yes --agent` | Delete inventoryasset (no prompt) |

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
