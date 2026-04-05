# FloorPlanLayoutNodes

<!-- BEGIN:GENERATED entity=FloorPlanLayoutNodes -->

FloorPlanLayoutNodes support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutnodes list --agent` | List all floorplanlayoutnodes |
| `nexudus floorplanlayoutnodes list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutnodes list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutnodes list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutnodes list --floor-plan-layout-id <value> --node-key <value> --agent` | Filter floorplanlayoutnodes by properties |
| `nexudus floorplanlayoutnodes list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutnodes get <id> --agent` | Get single floorplanlayoutnode |
| `nexudus floorplanlayoutnodes create --floor-plan-layout-id <value> --pos-x <value> --pos-y <value> --agent` | Create floorplanlayoutnode |
| `nexudus floorplanlayoutnodes update <id> --name "New Name" --agent` | Update floorplanlayoutnode |
| `nexudus floorplanlayoutnodes delete <id> --yes --agent` | Delete floorplanlayoutnode (no prompt) |

#### FloorPlanLayoutNode list filter options

`--floor-plan-layout-id`, `--node-key`, `--pos-x`, `--from-pos-x` (range), `--to-pos-x` (range), `--pos-y`, `--from-pos-y` (range), `--to-pos-y` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanLayoutNode create options

`--floor-plan-layout-id` (required), `--node-key`, `--pos-x` (required), `--pos-y` (required)

#### FloorPlanLayoutNode update options

`--floor-plan-layout-id`, `--node-key`, `--pos-x`, `--pos-y`

<!-- END:GENERATED entity=FloorPlanLayoutNodes -->
