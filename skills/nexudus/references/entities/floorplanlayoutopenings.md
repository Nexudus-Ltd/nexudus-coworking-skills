# FloorPlanLayoutOpenings

<!-- BEGIN:GENERATED entity=FloorPlanLayoutOpenings -->

A **FloorPlanLayoutOpening** represents a door, window, or other opening in a floor plan layout wall or boundary edge.

FloorPlanLayoutOpenings support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutopenings list --agent` | List all floorplanlayoutopenings |
| `nexudus floorplanlayoutopenings list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutopenings list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutopenings list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutopenings list --floor-plan-layout-edge-id <value> --floor-plan-layout-edge-name <value> --agent` | Filter floorplanlayoutopenings by properties |
| `nexudus floorplanlayoutopenings list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutopenings list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplanlayoutopenings get <id> --agent` | Get single floorplanlayoutopening |
| `nexudus floorplanlayoutopenings create --floor-plan-layout-edge-id <value> --opening-type <value> --floor-offset <value> --start <value> --height <value> --length <value> --agent` | Create floorplanlayoutopening |
| `nexudus floorplanlayoutopenings update <id> --name "New Name" --agent` | Update floorplanlayoutopening |
| `nexudus floorplanlayoutopenings delete <id> --yes --agent` | Delete floorplanlayoutopening (no prompt) |

#### FloorPlanLayoutOpening list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-edge-id` | long | ID of the floor plan layout edge linked to this record |
| `--floor-plan-layout-edge-name` | string | Display name of the linked floor plan layout edge (read-only) |
| `--opening-type` | string | The opening type value for this floor plan layout opening |
| `--floor-offset` | int | The floor offset value for this floor plan layout opening |
| `--from-floor-offset` | range | |
| `--to-floor-offset` | range | |
| `--start` | int | The start value for this floor plan layout opening |
| `--from-start` | range | |
| `--to-start` | range | |
| `--height` | int | The height value for this floor plan layout opening |
| `--from-height` | range | |
| `--to-height` | range | |
| `--length` | int | The length value for this floor plan layout opening |
| `--from-length` | range | |
| `--to-length` | range | |
| `--hinge` | string | The hinge value for this floor plan layout opening |
| `--door-type` | string | The door type value for this floor plan layout opening |
| `--door-arc-angle` | int | The door arc angle value for this floor plan layout opening |
| `--from-door-arc-angle` | range | |
| `--to-door-arc-angle` | range | |
| `--door-is-locked` | bool | Whether door is locked is enabled |
| `--window-pane-count` | int | The window pane count value for this floor plan layout opening |
| `--from-window-pane-count` | range | |
| `--to-window-pane-count` | range | |
| `--direction` | string | The direction value for this floor plan layout opening |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutOpening sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlanLayoutOpening create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-edge-id` | long, required | ID of the floor plan layout edge linked to this record |
| `--opening-type` | string, required | The opening type value for this floor plan layout opening |
| `--floor-offset` | int, required | The floor offset value for this floor plan layout opening |
| `--start` | int, required | The start value for this floor plan layout opening |
| `--height` | int, required | The height value for this floor plan layout opening |
| `--length` | int, required | The length value for this floor plan layout opening |
| `--hinge` | string | The hinge value for this floor plan layout opening |
| `--door-type` | string | The door type value for this floor plan layout opening |
| `--door-arc-angle` | int | The door arc angle value for this floor plan layout opening |
| `--door-is-locked` | bool | Whether door is locked is enabled |
| `--window-pane-count` | int | The window pane count value for this floor plan layout opening |
| `--direction` | string | The direction value for this floor plan layout opening |

#### FloorPlanLayoutOpening update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-edge-id` | long | ID of the floor plan layout edge linked to this record |
| `--opening-type` | string | The opening type value for this floor plan layout opening |
| `--floor-offset` | int | The floor offset value for this floor plan layout opening |
| `--start` | int | The start value for this floor plan layout opening |
| `--height` | int | The height value for this floor plan layout opening |
| `--length` | int | The length value for this floor plan layout opening |
| `--hinge` | string | The hinge value for this floor plan layout opening |
| `--door-type` | string | The door type value for this floor plan layout opening |
| `--door-arc-angle` | int | The door arc angle value for this floor plan layout opening |
| `--door-is-locked` | bool | Whether door is locked is enabled |
| `--window-pane-count` | int | The window pane count value for this floor plan layout opening |
| `--direction` | string | The direction value for this floor plan layout opening |

<!-- END:GENERATED entity=FloorPlanLayoutOpenings -->
