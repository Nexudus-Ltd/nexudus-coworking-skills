# FloorPlanLayoutEdges

<!-- BEGIN:GENERATED entity=FloorPlanLayoutEdges -->

A **FloorPlanLayoutEdge** represents a connection or boundary line between nodes in a floor plan layout, used to define walls, pathways, or other structural elements.

FloorPlanLayoutEdges support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutedges list --agent` | List all floorplanlayoutedges |
| `nexudus floorplanlayoutedges list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutedges list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutedges list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutedges list --floor-plan-layout-id <value> --edge-key <value> --agent` | Filter floorplanlayoutedges by properties |
| `nexudus floorplanlayoutedges list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutedges get <id> --agent` | Get single floorplanlayoutedge |
| `nexudus floorplanlayoutedges create --floor-plan-layout-id <value> --angle <value> --width <value> --height <value> --length <value> --agent` | Create floorplanlayoutedge |
| `nexudus floorplanlayoutedges update <id> --name "New Name" --agent` | Update floorplanlayoutedge |
| `nexudus floorplanlayoutedges delete <id> --yes --agent` | Delete floorplanlayoutedge (no prompt) |

#### FloorPlanLayoutEdge list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--edge-key` | string | The edge key value for this floor plan layout edge |
| `--source` | string | The source value for this floor plan layout edge |
| `--target` | string | The target value for this floor plan layout edge |
| `--angle` | decimal | The angle value for this floor plan layout edge |
| `--from-angle` | range | |
| `--to-angle` | range | |
| `--width` | int | The width value for this floor plan layout edge |
| `--from-width` | range | |
| `--to-width` | range | |
| `--height` | int | The height value for this floor plan layout edge |
| `--from-height` | range | |
| `--to-height` | range | |
| `--length` | int | The length value for this floor plan layout edge |
| `--from-length` | range | |
| `--to-length` | range | |
| `--is-partition` | bool | Whether is partition is enabled |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutEdge create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required | ID of the floor plan layout linked to this record |
| `--edge-key` | string | The edge key value for this floor plan layout edge |
| `--source` | string | The source value for this floor plan layout edge |
| `--target` | string | The target value for this floor plan layout edge |
| `--angle` | decimal, required | The angle value for this floor plan layout edge |
| `--width` | int, required | The width value for this floor plan layout edge |
| `--height` | int, required | The height value for this floor plan layout edge |
| `--length` | int, required | The length value for this floor plan layout edge |
| `--is-partition` | bool | Whether is partition is enabled |

#### FloorPlanLayoutEdge update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--edge-key` | string | The edge key value for this floor plan layout edge |
| `--source` | string | The source value for this floor plan layout edge |
| `--target` | string | The target value for this floor plan layout edge |
| `--angle` | decimal | The angle value for this floor plan layout edge |
| `--width` | int | The width value for this floor plan layout edge |
| `--height` | int | The height value for this floor plan layout edge |
| `--length` | int | The length value for this floor plan layout edge |
| `--is-partition` | bool | Whether is partition is enabled |

<!-- END:GENERATED entity=FloorPlanLayoutEdges -->
