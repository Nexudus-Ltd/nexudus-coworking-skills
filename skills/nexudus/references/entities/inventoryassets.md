# InventoryAssets

<!-- BEGIN:GENERATED entity=InventoryAssets -->

An InventoryAsset is a location-owned physical item, such as a desk, chair, monitor, or printer, tracked at the location, a bookable resource, or a floor-plan desk. Customer assignments are managed as separate CoworkerInventoryAsset records.

InventoryAssets support Search, Get, Create, Update, Delete.
InventoryAssets also support entity commands.

| Command | Description |
| --- | --- |
| `nexudus inventoryassets list --agent` | List all inventoryassets |
| `nexudus inventoryassets list --id <id> --agent` | Filter by single ID |
| `nexudus inventoryassets list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus inventoryassets list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus inventoryassets list --business-name <value> --name <value> --agent` | Filter inventoryassets by properties |
| `nexudus inventoryassets list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus inventoryassets list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus inventoryassets get <id> --agent` | Get single inventoryasset |
| `nexudus inventoryassets create --business-id <value> --name <value> --assign-to-type <value> --agent` | Create inventoryasset |
| `nexudus inventoryassets update <id> --name "New Name" --agent` | Update inventoryasset |
| `nexudus inventoryassets delete <id> --yes --agent` | Delete inventoryasset (no prompt) |
| `nexudus inventoryassets run-command <key> <ids> --agent` | Run entity command |

#### InventoryAsset list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this asset; saving a linked resource or floor-plan desk can replace it with that linked record's location. |
| `--business-name` | string | Name of the location this asset belongs to |
| `--name` | string | Required display name of the physical asset, such as 'Standing Desk #3' or 'HP LaserJet'. |
| `--description` | string | Optional free-text description of the asset. |
| `--sku` | string | Optional stock-keeping unit code; when provided, it must be unique within the location. |
| `--image-file-name` | string | Current file name of the image (read-only; upload via the corresponding URL field) |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--value` | decimal | Optional monetary value of the asset in the owning location's currency. |
| `--from-value` | range | |
| `--to-value` | range | |
| `--floor-plan-desk-id` | long | ID of the floor-plan desk linked to this asset; required when AssignToType is FloorPlanItem and it sets the asset's location from the desk's floor plan. |
| `--floor-plan-desk-name` | string | Name of the linked floor-plan desk |
| `--coworker-full-names` | string | Read-only comma-separated customer names projected from CoworkerInventoryAsset assignment records; change assignments through that entity instead. |
| `--coworker-ids` | string | Read-only comma-separated customer IDs projected from CoworkerInventoryAsset assignment records; change assignments through that entity instead. |
| `--coworker-start-dates` | string | Read-only comma-separated assignment start dates projected from CoworkerInventoryAsset records; each assignment requires a start date. |
| `--coworker-end-dates` | string | Read-only comma-separated assignment end dates projected from CoworkerInventoryAsset records; an end date cannot precede its assignment start date. |
| `--resource-id` | long | ID of the bookable resource linked to this asset; required when AssignToType is Resource and it sets the asset's location to the resource's location. |
| `--resource-name` | string | Name of the linked bookable resource |
| `--assign-to-type` | enum | Determines the asset scope: Location (1) needs no linked resource or desk, Resource (2) requires ResourceId, and FloorPlanItem (3) requires FloorPlanDeskId. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### InventoryAsset sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### InventoryAsset create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this asset; saving a linked resource or floor-plan desk can replace it with that linked record's location. |
| `--name` | string, required | Required display name of the physical asset, such as 'Standing Desk #3' or 'HP LaserJet'. |
| `--description` | string | Optional free-text description of the asset. |
| `--sku` | string | Optional stock-keeping unit code; when provided, it must be unique within the location. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--value` | decimal | Optional monetary value of the asset in the owning location's currency. |
| `--floor-plan-desk-id` | long | ID of the floor-plan desk linked to this asset; required when AssignToType is FloorPlanItem and it sets the asset's location from the desk's floor plan. |
| `--resource-id` | long | ID of the bookable resource linked to this asset; required when AssignToType is Resource and it sets the asset's location to the resource's location. |
| `--assign-to-type` | enum, required | Determines the asset scope: Location (1) needs no linked resource or desk, Resource (2) requires ResourceId, and FloorPlanItem (3) requires FloorPlanDeskId. |

#### InventoryAsset update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this asset; saving a linked resource or floor-plan desk can replace it with that linked record's location. |
| `--name` | string | Required display name of the physical asset, such as 'Standing Desk #3' or 'HP LaserJet'. |
| `--description` | string | Optional free-text description of the asset. |
| `--sku` | string | Optional stock-keeping unit code; when provided, it must be unique within the location. |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--value` | decimal | Optional monetary value of the asset in the owning location's currency. |
| `--floor-plan-desk-id` | long | ID of the floor-plan desk linked to this asset; required when AssignToType is FloorPlanItem and it sets the asset's location from the desk's floor plan. |
| `--resource-id` | long | ID of the bookable resource linked to this asset; required when AssignToType is Resource and it sets the asset's location to the resource's location. |
| `--assign-to-type` | enum | Determines the asset scope: Location (1) needs no linked resource or desk, Resource (2) requires ResourceId, and FloorPlanItem (3) requires FloorPlanDeskId. |

#### InventoryAsset PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus inventoryassets update <id> --coworker-full-names "«PII:NAME:a3f2b1c9»" --agent`

### InventoryAsset (key fields)

`Id`, `BusinessName`, `Name`

#### InventoryAsset enum values

| Option | Valid values |
| ------ | ------------ |
| `--assign-to-type` | `1` Location, `2` Resource, `3` FloorPlanItem |

<!-- END:GENERATED entity=InventoryAssets -->
