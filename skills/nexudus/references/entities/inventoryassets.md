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
| `nexudus inventoryassets create --business-id <value> --name <value> --assign-to-type <value> --agent` | Create inventoryasset |
| `nexudus inventoryassets update <id> --name "New Name" --agent` | Update inventoryasset |
| `nexudus inventoryassets delete <id> --yes --agent` | Delete inventoryasset (no prompt) |
| `nexudus inventoryassets run-command <key> <ids> --agent` | Run entity command |

#### InventoryAsset list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Display name of the asset (e.g. 'Standing Desk #3', 'HP LaserJet') |
| `--description` | string | Free-text description of the asset |
| `--sku` | string | Stock-keeping unit code for the asset |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--value` | decimal | Monetary value of the asset |
| `--from-value` | range | |
| `--to-value` | range | |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--resource-id` | long | ID of the resource linked to this record |
| `--assign-to-type` | enum | Determines what this asset is assigned to: Location (1), Resource (2), or FloorPlanItem (3) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### InventoryAsset create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | Display name of the asset (e.g. 'Standing Desk #3', 'HP LaserJet') |
| `--description` | string | Free-text description of the asset |
| `--sku` | string | Stock-keeping unit code for the asset |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--value` | decimal | Monetary value of the asset |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--resource-id` | long | ID of the resource linked to this record |
| `--assign-to-type` | enum, required | Determines what this asset is assigned to: Location (1), Resource (2), or FloorPlanItem (3) |

#### InventoryAsset update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | Display name of the asset (e.g. 'Standing Desk #3', 'HP LaserJet') |
| `--description` | string | Free-text description of the asset |
| `--sku` | string | Stock-keeping unit code for the asset |
| `--new-image-url` | string | URL of a new file to upload as the image |
| `--clear-image-file` | bool | Set to true to remove the current image file |
| `--value` | decimal | Monetary value of the asset |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--resource-id` | long | ID of the resource linked to this record |
| `--assign-to-type` | enum | Determines what this asset is assigned to: Location (1), Resource (2), or FloorPlanItem (3) |

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
