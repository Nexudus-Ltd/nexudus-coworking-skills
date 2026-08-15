# ResourceTypes

<!-- BEGIN:GENERATED entity=ResourceTypes -->

A resource type categorizes bookable resources (e.g., Meeting Room, Hot Desk, or Private Office). Each resource belongs to one resource type. Pricing is not stored on the resource type: booking rates (ExtraService records) apply through their ResourceTypes relationship, and every resource assigned to the type inherits those rates.

ResourceTypes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus resourcetypes list --agent` | List all resourcetypes |
| `nexudus resourcetypes list --id <id> --agent` | Filter by single ID |
| `nexudus resourcetypes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus resourcetypes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus resourcetypes list --name <value> --agent` | Filter resourcetypes by properties |
| `nexudus resourcetypes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus resourcetypes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus resourcetypes get <id> --agent` | Get single resourcetype |
| `nexudus resourcetypes create --business-id <value> --name <value> --agent` | Create resourcetype |
| `nexudus resourcetypes update <id> --name "New Name" --agent` | Update resourcetype |
| `nexudus resourcetypes delete <id> --yes --agent` | Delete resourcetype (no prompt) |

#### ResourceType list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this resource type. Resources and booking rates assigned to the type should belong to this location. |
| `--name` | string | Display name of the resource category (e.g., 'Meeting Room', 'Hot Desk', or 'Private Office'). Resources that share this type also share the booking rates linked to it. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ResourceType sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ResourceType create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this resource type. Resources and booking rates assigned to the type should belong to this location. |
| `--name` | string, required | Display name of the resource category (e.g., 'Meeting Room', 'Hot Desk', or 'Private Office'). Resources that share this type also share the booking rates linked to it. |

#### ResourceType update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this resource type. Resources and booking rates assigned to the type should belong to this location. |
| `--name` | string | Display name of the resource category (e.g., 'Meeting Room', 'Hot Desk', or 'Private Office'). Resources that share this type also share the booking rates linked to it. |

### ResourceType (key fields)

`Id`, `Name`

<!-- END:GENERATED entity=ResourceTypes -->
