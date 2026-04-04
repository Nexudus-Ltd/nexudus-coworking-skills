# FloorPlanLayoutOpenings

<!-- BEGIN:GENERATED entity=FloorPlanLayoutOpenings -->

FloorPlanLayoutOpenings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutopenings list --agent` | List all floorplanlayoutopenings |
| `nexudus floorplanlayoutopenings list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutopenings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutopenings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutopenings list --floor-plan-layout-edge-id <value> --opening-type <value> --agent` | Filter floorplanlayoutopenings by properties |
| `nexudus floorplanlayoutopenings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutopenings get <id> --agent` | Get single floorplanlayoutopening |
| `nexudus floorplanlayoutopenings create --floor-plan-layout-edge-id <value> --opening-type <value> --floor-offset <value> --start <value> --height <value> --length <value> --agent` | Create floorplanlayoutopening |
| `nexudus floorplanlayoutopenings update <id> --name "New Name" --agent` | Update floorplanlayoutopening |
| `nexudus floorplanlayoutopenings delete <id> --yes --agent` | Delete floorplanlayoutopening (no prompt) |

#### FloorPlanLayoutOpening list filter options

`--floor-plan-layout-edge-id`, `--opening-type`, `--floor-offset`, `--start`, `--height`, `--length`, `--hinge`, `--door-type`, `--door-arc-angle`, `--door-is-locked`, `--window-pane-count`, `--direction`

#### FloorPlanLayoutOpening create options

`--floor-plan-layout-edge-id` (required), `--opening-type` (required), `--floor-offset` (required), `--start` (required), `--height` (required), `--length` (required), `--hinge`, `--door-type`, `--door-arc-angle`, `--door-is-locked`, `--window-pane-count`, `--direction`

#### FloorPlanLayoutOpening update options

`--floor-plan-layout-edge-id`, `--opening-type`, `--floor-offset`, `--start`, `--height`, `--length`, `--hinge`, `--door-type`, `--door-arc-angle`, `--door-is-locked`, `--window-pane-count`, `--direction`

<!-- END:GENERATED entity=FloorPlanLayoutOpenings -->
