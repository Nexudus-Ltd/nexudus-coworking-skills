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

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long |  |
| `--area-unique-id` | string |  |
| `--name` | string |  |
| `--transition-type` | string |  |
| `--transition-to` | string |  |
| `--angle` | decimal |  |
| `--from-angle` | range | |
| `--to-angle` | range | |
| `--height` | int |  |
| `--from-height` | range | |
| `--to-height` | range | |
| `--length` | int |  |
| `--from-length` | range | |
| `--to-length` | range | |
| `--width` | int |  |
| `--from-width` | range | |
| `--to-width` | range | |
| `--pos-x` | int |  |
| `--from-pos-x` | range | |
| `--to-pos-x` | range | |
| `--pos-y` | int |  |
| `--from-pos-y` | range | |
| `--to-pos-y` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorplanLayoutTransition create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required |  |
| `--area-unique-id` | string |  |
| `--name` | string |  |
| `--transition-type` | string, required |  |
| `--transition-to` | string |  |
| `--angle` | decimal, required |  |
| `--height` | int, required |  |
| `--length` | int, required |  |
| `--width` | int, required |  |
| `--pos-x` | int, required |  |
| `--pos-y` | int, required |  |

#### FloorplanLayoutTransition update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long |  |
| `--area-unique-id` | string |  |
| `--name` | string |  |
| `--transition-type` | string |  |
| `--transition-to` | string |  |
| `--angle` | decimal |  |
| `--height` | int |  |
| `--length` | int |  |
| `--width` | int |  |
| `--pos-x` | int |  |
| `--pos-y` | int |  |

<!-- END:GENERATED entity=FloorplanLayoutTransitions -->
