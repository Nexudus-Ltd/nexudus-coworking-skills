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

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-edge-id` | long |  |
| `--opening-type` | string |  |
| `--floor-offset` | int |  |
| `--from-floor-offset` | range | |
| `--to-floor-offset` | range | |
| `--start` | int |  |
| `--from-start` | range | |
| `--to-start` | range | |
| `--height` | int |  |
| `--from-height` | range | |
| `--to-height` | range | |
| `--length` | int |  |
| `--from-length` | range | |
| `--to-length` | range | |
| `--hinge` | string |  |
| `--door-type` | string |  |
| `--door-arc-angle` | int |  |
| `--from-door-arc-angle` | range | |
| `--to-door-arc-angle` | range | |
| `--door-is-locked` | bool |  |
| `--window-pane-count` | int |  |
| `--from-window-pane-count` | range | |
| `--to-window-pane-count` | range | |
| `--direction` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutOpening create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-edge-id` | long, required |  |
| `--opening-type` | string, required |  |
| `--floor-offset` | int, required |  |
| `--start` | int, required |  |
| `--height` | int, required |  |
| `--length` | int, required |  |
| `--hinge` | string |  |
| `--door-type` | string |  |
| `--door-arc-angle` | int |  |
| `--door-is-locked` | bool |  |
| `--window-pane-count` | int |  |
| `--direction` | string |  |

#### FloorPlanLayoutOpening update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-edge-id` | long |  |
| `--opening-type` | string |  |
| `--floor-offset` | int |  |
| `--start` | int |  |
| `--height` | int |  |
| `--length` | int |  |
| `--hinge` | string |  |
| `--door-type` | string |  |
| `--door-arc-angle` | int |  |
| `--door-is-locked` | bool |  |
| `--window-pane-count` | int |  |
| `--direction` | string |  |

<!-- END:GENERATED entity=FloorPlanLayoutOpenings -->
