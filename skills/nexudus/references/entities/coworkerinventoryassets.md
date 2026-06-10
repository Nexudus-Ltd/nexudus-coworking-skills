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
| `nexudus coworkerinventoryassets list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkerinventoryassets get <id> --agent` | Get single coworkerinventoryasset |
| `nexudus coworkerinventoryassets create --coworker-id <value> --business-id <value> --inventory-asset-id <value> --assigned-from <value> --agent` | Create coworkerinventoryasset |
| `nexudus coworkerinventoryassets update <id> --name "New Name" --agent` | Update coworkerinventoryasset |
| `nexudus coworkerinventoryassets delete <id> --yes --agent` | Delete coworkerinventoryasset (no prompt) |
| `nexudus coworkerinventoryassets run-command <key> <ids> --agent` | Run entity command |

#### CoworkerInventoryAsset list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--inventory-asset-id` | long | ID of the inventory asset linked to this record |
| `--notes` | string | Free-text notes about this asset assignment |
| `--assigned-from` | DateTime | Date the asset was assigned to the customer |
| `--from-assigned-from` | range | |
| `--to-assigned-from` | range | |
| `--assigned-to` | DateTime | Date the asset assignment ends. Null if still assigned |
| `--from-assigned-to` | range | |
| `--to-assigned-to` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerInventoryAsset sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `CreatedOn` ascending. If no `--order-by` is specified, the API returns results ordered by `CreatedOn` (ascending).

#### CoworkerInventoryAsset create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--business-id` | long, required | ID of the business linked to this record |
| `--inventory-asset-id` | long, required | ID of the inventory asset linked to this record |
| `--notes` | string | Free-text notes about this asset assignment |
| `--assigned-from` | DateTime, required | Date the asset was assigned to the customer |
| `--assigned-to` | DateTime | Date the asset assignment ends. Null if still assigned |

#### CoworkerInventoryAsset update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--business-id` | long | ID of the business linked to this record |
| `--inventory-asset-id` | long | ID of the inventory asset linked to this record |
| `--notes` | string | Free-text notes about this asset assignment |
| `--assigned-from` | DateTime | Date the asset was assigned to the customer |
| `--assigned-to` | DateTime | Date the asset assignment ends. Null if still assigned |

#### CoworkerInventoryAsset PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkerinventoryassets update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerInventoryAsset (key fields)

`Id`, `CoworkerFullName`, `InventoryAssetName`

<!-- END:GENERATED entity=CoworkerInventoryAssets -->
