# CoworkerInventoryAssets

<!-- BEGIN:GENERATED entity=CoworkerInventoryAssets -->

A customer equipment assignment links one customer to one equipment item at a location, with a required start and optional end date; use it for assignment history, planned returns, or notes rather than editing the equipment item's read-only assignment summaries.

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
| `--coworker-id` | long | ID of the customer receiving the equipment item; the customer must be accessible to the current user. |
| `--business-id` | long | ID of the location where this customer equipment assignment applies. |
| `--inventory-asset-id` | long | ID of the equipment item assigned to the customer; a customer cannot have more than one active assignment for the same item. |
| `--notes` | string | Optional internal notes about this customer equipment assignment. |
| `--assigned-from` | DateTime | Required assignment start date and time; the server rejects the record when it is not supplied. |
| `--from-assigned-from` | range | |
| `--to-assigned-from` | range | |
| `--assigned-to` | DateTime | Optional assignment end date and time, which cannot be earlier than AssignedFrom; null keeps the assignment active. |
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
| `--coworker-id` | long, required | ID of the customer receiving the equipment item; the customer must be accessible to the current user. |
| `--business-id` | long, required | ID of the location where this customer equipment assignment applies. |
| `--inventory-asset-id` | long, required | ID of the equipment item assigned to the customer; a customer cannot have more than one active assignment for the same item. |
| `--notes` | string | Optional internal notes about this customer equipment assignment. |
| `--assigned-from` | DateTime, required | Required assignment start date and time; the server rejects the record when it is not supplied. |
| `--assigned-to` | DateTime | Optional assignment end date and time, which cannot be earlier than AssignedFrom; null keeps the assignment active. |

#### CoworkerInventoryAsset update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer receiving the equipment item; the customer must be accessible to the current user. |
| `--business-id` | long | ID of the location where this customer equipment assignment applies. |
| `--inventory-asset-id` | long | ID of the equipment item assigned to the customer; a customer cannot have more than one active assignment for the same item. |
| `--notes` | string | Optional internal notes about this customer equipment assignment. |
| `--assigned-from` | DateTime | Required assignment start date and time; the server rejects the record when it is not supplied. |
| `--assigned-to` | DateTime | Optional assignment end date and time, which cannot be earlier than AssignedFrom; null keeps the assignment active. |

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
