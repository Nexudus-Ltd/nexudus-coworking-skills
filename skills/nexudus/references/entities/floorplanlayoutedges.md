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

`--floor-plan-layout-id`, `--edge-key`, `--source`, `--target`, `--angle`, `--from-angle` (range), `--to-angle` (range), `--width`, `--from-width` (range), `--to-width` (range), `--height`, `--from-height` (range), `--to-height` (range), `--length`, `--from-length` (range), `--to-length` (range), `--is-partition`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanLayoutEdge create options

`--floor-plan-layout-id` (required), `--edge-key`, `--source`, `--target`, `--angle` (required), `--width` (required), `--height` (required), `--length` (required), `--is-partition`

#### FloorPlanLayoutEdge update options

`--floor-plan-layout-id`, `--edge-key`, `--source`, `--target`, `--angle`, `--width`, `--height`, `--length`, `--is-partition`

<!-- END:GENERATED entity=FloorPlanLayoutEdges -->
