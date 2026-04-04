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

`--floor-plan-layout-id`, `--edge-key`, `--source`, `--target`, `--angle`, `--width`, `--height`, `--length`, `--is-partition`

#### FloorPlanLayoutEdge create options

`--floor-plan-layout-id` (required), `--edge-key`, `--source`, `--target`, `--angle` (required), `--width` (required), `--height` (required), `--length` (required), `--is-partition`, `--openings` (list, repeat flag), `--added-openings` (list, repeat flag), `--removed-openings` (list, repeat flag)

#### FloorPlanLayoutEdge update options

`--floor-plan-layout-id`, `--edge-key`, `--source`, `--target`, `--angle`, `--width`, `--height`, `--length`, `--is-partition`, `--openings` (list, repeat flag), `--added-openings` (list, repeat flag), `--removed-openings` (list, repeat flag)

**List properties (only returned by `get`, not by `list`):** `Openings`, `AddedOpenings`, `RemovedOpenings`

<!-- END:GENERATED entity=FloorPlanLayoutEdges -->
