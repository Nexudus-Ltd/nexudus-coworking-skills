# ResourceTypes

<!-- BEGIN:GENERATED entity=ResourceTypes -->

A **ResourceType** is a category of bookable space (e.g., "Meeting Room", "Phone Booth", "Hot Desk"). Every `Resource` must be assigned to exactly one resource type. Pricing for a resource type is not stored on the type itself — it is defined by `ExtraService` records that reference the type. Multiple extra services can apply to the same resource type, covering different charge periods or customer restrictions.

ResourceTypes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourcetypes list --agent` | List all resourcetypes |
| `nexudus resourcetypes list --query "search" --agent` | Search resourcetypes by name |
| `nexudus resourcetypes list --page 2 --size 10 --agent` | Paginated list |
| `nexudus resourcetypes get <id> --agent` | Get single resourcetype |
| `nexudus resourcetypes create --business <value> --name <value> --agent` | Create resourcetype |
| `nexudus resourcetypes update <id> --name "New Name" --agent` | Update resourcetype |
| `nexudus resourcetypes delete <id> --yes --agent` | Delete resourcetype (no prompt) |

#### ResourceType create options

`--business` (required), `--name` (required)

#### ResourceType update options

`--name`

### ResourceType (key fields)

`Id`, `BusinessId`, `BusinessName`, `Name`

<!-- END:GENERATED entity=ResourceTypes -->
