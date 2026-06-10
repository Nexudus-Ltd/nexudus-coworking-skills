# FloorPlanLayoutNodes

<!-- BEGIN:GENERATED entity=FloorPlanLayoutNodes -->

A **FloorPlanLayoutNode** represents a point or vertex in a floor plan layout, used as an anchor for edges, openings, and other structural elements.

FloorPlanLayoutNodes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutnodes list --agent` | List all floorplanlayoutnodes |
| `nexudus floorplanlayoutnodes list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutnodes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutnodes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutnodes list --floor-plan-layout-id <value> --node-key <value> --agent` | Filter floorplanlayoutnodes by properties |
| `nexudus floorplanlayoutnodes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutnodes list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplanlayoutnodes get <id> --agent` | Get single floorplanlayoutnode |
| `nexudus floorplanlayoutnodes create --floor-plan-layout-id <value> --pos-x <value> --pos-y <value> --agent` | Create floorplanlayoutnode |
| `nexudus floorplanlayoutnodes update <id> --name "New Name" --agent` | Update floorplanlayoutnode |
| `nexudus floorplanlayoutnodes delete <id> --yes --agent` | Delete floorplanlayoutnode (no prompt) |

#### FloorPlanLayoutNode list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--node-key` | string | The node key value for this floor plan layout node |
| `--pos-x` | int | The x value for this floor plan layout node |
| `--from-pos-x` | range | |
| `--to-pos-x` | range | |
| `--pos-y` | int | The y value for this floor plan layout node |
| `--from-pos-y` | range | |
| `--to-pos-y` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutNode sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlanLayoutNode create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required | ID of the floor plan layout linked to this record |
| `--node-key` | string | The node key value for this floor plan layout node |
| `--pos-x` | int, required | The x value for this floor plan layout node |
| `--pos-y` | int, required | The y value for this floor plan layout node |

#### FloorPlanLayoutNode update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--node-key` | string | The node key value for this floor plan layout node |
| `--pos-x` | int | The x value for this floor plan layout node |
| `--pos-y` | int | The y value for this floor plan layout node |

<!-- END:GENERATED entity=FloorPlanLayoutNodes -->
