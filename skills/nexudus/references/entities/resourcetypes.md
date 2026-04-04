# ResourceTypes

<!-- BEGIN:GENERATED entity=ResourceTypes -->

A **ResourceType** is a category of bookable space (e.g., "Meeting Room", "Phone Booth", "Hot Desk"). Every `Resource` must be assigned to exactly one resource type. Pricing for a resource type is not stored on the type itself — it is defined by `ExtraService` records that reference the type. Multiple extra services can apply to the same resource type, covering different charge periods or customer restrictions.

ResourceTypes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourcetypes list --agent` | List all resourcetypes |
| `nexudus resourcetypes list --id <id> --agent` | Filter by single ID |
| `nexudus resourcetypes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resourcetypes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resourcetypes list --name <value> --agent` | Filter resourcetypes by properties |
| `nexudus resourcetypes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resourcetypes get <id> --agent` | Get single resourcetype |
| `nexudus resourcetypes create --business-id <value> --name <value> --agent` | Create resourcetype |
| `nexudus resourcetypes update <id> --name "New Name" --agent` | Update resourcetype |
| `nexudus resourcetypes delete <id> --yes --agent` | Delete resourcetype (no prompt) |

#### ResourceType list filter options

`--business-id`, `--name`

#### ResourceType create options

`--business-id` (required), `--name` (required), `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag)

#### ResourceType update options

`--business-id`, `--name`, `--resources` (list, repeat flag), `--added-resources` (list, repeat flag), `--removed-resources` (list, repeat flag)

### ResourceType (key fields)

`Id`, `Name`

**List properties (only returned by `get`, not by `list`):** `Resources`, `AddedResources`, `RemovedResources`

<!-- END:GENERATED entity=ResourceTypes -->
