# FloorPlanLayoutAssets

<!-- BEGIN:GENERATED entity=FloorPlanLayoutAssets -->

A **FloorPlanLayoutAsset** positions a physical asset within a specific floor plan layout, defining its coordinates, rotation, and visual properties on the plan.

FloorPlanLayoutAssets support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutassets list --agent` | List all floorplanlayoutassets |
| `nexudus floorplanlayoutassets list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutassets list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutassets list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutassets list --floor-plan-layout-id <value> --floor-plan-layout-name <value> --agent` | Filter floorplanlayoutassets by properties |
| `nexudus floorplanlayoutassets list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutassets list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplanlayoutassets get <id> --agent` | Get single floorplanlayoutasset |
| `nexudus floorplanlayoutassets create --floor-plan-layout-id <value> --angle <value> --height <value> --length <value> --width <value> --pos-x <value> --pos-y <value> --floor-offset <value> --agent` | Create floorplanlayoutasset |
| `nexudus floorplanlayoutassets update <id> --name "New Name" --agent` | Update floorplanlayoutasset |
| `nexudus floorplanlayoutassets delete <id> --yes --agent` | Delete floorplanlayoutasset (no prompt) |

#### FloorPlanLayoutAsset list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--floor-plan-layout-name` | string | Display name of the linked floor plan layout (read-only) |
| `--area-unique-id` | string | ID of the area unique associated with this record |
| `--asset-type` | string | The asset type value for this floor plan layout asset |
| `--angle` | decimal | The angle value for this floor plan layout asset |
| `--from-angle` | range | |
| `--to-angle` | range | |
| `--height` | int | The height value for this floor plan layout asset |
| `--from-height` | range | |
| `--to-height` | range | |
| `--length` | int | The length value for this floor plan layout asset |
| `--from-length` | range | |
| `--to-length` | range | |
| `--width` | int | The width value for this floor plan layout asset |
| `--from-width` | range | |
| `--to-width` | range | |
| `--pos-x` | int | The x value for this floor plan layout asset |
| `--from-pos-x` | range | |
| `--to-pos-x` | range | |
| `--pos-y` | int | The y value for this floor plan layout asset |
| `--from-pos-y` | range | |
| `--to-pos-y` | range | |
| `--floor-offset` | int | The floor offset value for this floor plan layout asset |
| `--from-floor-offset` | range | |
| `--to-floor-offset` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutAsset sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlanLayoutAsset create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required | ID of the floor plan layout linked to this record |
| `--area-unique-id` | string | ID of the area unique associated with this record |
| `--asset-type` | string | The asset type value for this floor plan layout asset |
| `--angle` | decimal, required | The angle value for this floor plan layout asset |
| `--height` | int, required | The height value for this floor plan layout asset |
| `--length` | int, required | The length value for this floor plan layout asset |
| `--width` | int, required | The width value for this floor plan layout asset |
| `--pos-x` | int, required | The x value for this floor plan layout asset |
| `--pos-y` | int, required | The y value for this floor plan layout asset |
| `--floor-offset` | int, required | The floor offset value for this floor plan layout asset |

#### FloorPlanLayoutAsset update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--area-unique-id` | string | ID of the area unique associated with this record |
| `--asset-type` | string | The asset type value for this floor plan layout asset |
| `--angle` | decimal | The angle value for this floor plan layout asset |
| `--height` | int | The height value for this floor plan layout asset |
| `--length` | int | The length value for this floor plan layout asset |
| `--width` | int | The width value for this floor plan layout asset |
| `--pos-x` | int | The x value for this floor plan layout asset |
| `--pos-y` | int | The y value for this floor plan layout asset |
| `--floor-offset` | int | The floor offset value for this floor plan layout asset |

<!-- END:GENERATED entity=FloorPlanLayoutAssets -->
