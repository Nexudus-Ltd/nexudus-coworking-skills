# FloorplanLayoutTransitions

<!-- BEGIN:GENERATED entity=FloorplanLayoutTransitions -->

A **FloorplanLayoutTransition** defines a navigation link between two floor plan layouts, representing staircases, elevators, or other transitions between floors or zones.

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
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--area-unique-id` | string | ID of the area unique associated with this record |
| `--name` | string | The name value for this floorplan layout transition |
| `--transition-type` | string | The transition type value for this floorplan layout transition |
| `--transition-to` | string | The transition to value for this floorplan layout transition |
| `--angle` | decimal | The angle value for this floorplan layout transition |
| `--from-angle` | range | |
| `--to-angle` | range | |
| `--height` | int | The height value for this floorplan layout transition |
| `--from-height` | range | |
| `--to-height` | range | |
| `--length` | int | The length value for this floorplan layout transition |
| `--from-length` | range | |
| `--to-length` | range | |
| `--width` | int | The width value for this floorplan layout transition |
| `--from-width` | range | |
| `--to-width` | range | |
| `--pos-x` | int | The x value for this floorplan layout transition |
| `--from-pos-x` | range | |
| `--to-pos-x` | range | |
| `--pos-y` | int | The y value for this floorplan layout transition |
| `--from-pos-y` | range | |
| `--to-pos-y` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorplanLayoutTransition create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required | ID of the floor plan layout linked to this record |
| `--area-unique-id` | string | ID of the area unique associated with this record |
| `--name` | string | The name value for this floorplan layout transition |
| `--transition-type` | string, required | The transition type value for this floorplan layout transition |
| `--transition-to` | string | The transition to value for this floorplan layout transition |
| `--angle` | decimal, required | The angle value for this floorplan layout transition |
| `--height` | int, required | The height value for this floorplan layout transition |
| `--length` | int, required | The length value for this floorplan layout transition |
| `--width` | int, required | The width value for this floorplan layout transition |
| `--pos-x` | int, required | The x value for this floorplan layout transition |
| `--pos-y` | int, required | The y value for this floorplan layout transition |

#### FloorplanLayoutTransition update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--area-unique-id` | string | ID of the area unique associated with this record |
| `--name` | string | The name value for this floorplan layout transition |
| `--transition-type` | string | The transition type value for this floorplan layout transition |
| `--transition-to` | string | The transition to value for this floorplan layout transition |
| `--angle` | decimal | The angle value for this floorplan layout transition |
| `--height` | int | The height value for this floorplan layout transition |
| `--length` | int | The length value for this floorplan layout transition |
| `--width` | int | The width value for this floorplan layout transition |
| `--pos-x` | int | The x value for this floorplan layout transition |
| `--pos-y` | int | The y value for this floorplan layout transition |

<!-- END:GENERATED entity=FloorplanLayoutTransitions -->
