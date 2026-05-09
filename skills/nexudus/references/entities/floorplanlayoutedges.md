# FloorPlanLayoutEdges

<!-- BEGIN:GENERATED entity=FloorPlanLayoutEdges -->

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
| `--floor-plan-layout-id` | long |  |
| `--edge-key` | string |  |
| `--source` | string |  |
| `--target` | string |  |
| `--angle` | decimal |  |
| `--from-angle` | range | |
| `--to-angle` | range | |
| `--width` | int |  |
| `--from-width` | range | |
| `--to-width` | range | |
| `--height` | int |  |
| `--from-height` | range | |
| `--to-height` | range | |
| `--length` | int |  |
| `--from-length` | range | |
| `--to-length` | range | |
| `--is-partition` | bool |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutEdge create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required |  |
| `--edge-key` | string |  |
| `--source` | string |  |
| `--target` | string |  |
| `--angle` | decimal, required |  |
| `--width` | int, required |  |
| `--height` | int, required |  |
| `--length` | int, required |  |
| `--is-partition` | bool |  |

#### FloorPlanLayoutEdge update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long |  |
| `--edge-key` | string |  |
| `--source` | string |  |
| `--target` | string |  |
| `--angle` | decimal |  |
| `--width` | int |  |
| `--height` | int |  |
| `--length` | int |  |
| `--is-partition` | bool |  |

<!-- END:GENERATED entity=FloorPlanLayoutEdges -->
