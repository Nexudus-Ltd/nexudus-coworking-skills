# FloorplanLayoutTransitions

<!-- BEGIN:GENERATED entity=FloorplanLayoutTransitions -->

FloorplanLayoutTransitions support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayouttransitions list --agent` | List all floorplanlayouttransitions |
| `nexudus floorplanlayouttransitions list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayouttransitions list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayouttransitions list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayouttransitions list --floor-plan-layout-id <value> --area-unique-id <value> --agent` | Filter floorplanlayouttransitions by properties |
| `nexudus floorplanlayouttransitions list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayouttransitions get <id> --agent` | Get single floorplanlayouttransition |
| `nexudus floorplanlayouttransitions create --floor-plan-layout-id <value> --transition-type <value> --angle <value> --height <value> --length <value> --width <value> --pos-x <value> --pos-y <value> --agent` | Create floorplanlayouttransition |
| `nexudus floorplanlayouttransitions update <id> --name "New Name" --agent` | Update floorplanlayouttransition |
| `nexudus floorplanlayouttransitions delete <id> --yes --agent` | Delete floorplanlayouttransition (no prompt) |

#### FloorplanLayoutTransition list filter options

`--floor-plan-layout-id`, `--area-unique-id`, `--name`, `--transition-type`, `--transition-to`, `--angle`, `--height`, `--length`, `--width`, `--pos-x`, `--pos-y`

#### FloorplanLayoutTransition create options

`--floor-plan-layout-id` (required), `--area-unique-id`, `--name`, `--transition-type` (required), `--transition-to`, `--angle` (required), `--height` (required), `--length` (required), `--width` (required), `--pos-x` (required), `--pos-y` (required)

#### FloorplanLayoutTransition update options

`--floor-plan-layout-id`, `--area-unique-id`, `--name`, `--transition-type`, `--transition-to`, `--angle`, `--height`, `--length`, `--width`, `--pos-x`, `--pos-y`

<!-- END:GENERATED entity=FloorplanLayoutTransitions -->
