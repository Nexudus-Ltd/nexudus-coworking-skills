# FloorPlanLayoutAssets

<!-- BEGIN:GENERATED entity=FloorPlanLayoutAssets -->

FloorPlanLayoutAssets support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutassets list --agent` | List all floorplanlayoutassets |
| `nexudus floorplanlayoutassets list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutassets list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutassets list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutassets list --floor-plan-layout-id <value> --area-unique-id <value> --agent` | Filter floorplanlayoutassets by properties |
| `nexudus floorplanlayoutassets list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutassets get <id> --agent` | Get single floorplanlayoutasset |
| `nexudus floorplanlayoutassets create --floor-plan-layout-id <value> --angle <value> --height <value> --length <value> --width <value> --pos-x <value> --pos-y <value> --floor-offset <value> --agent` | Create floorplanlayoutasset |
| `nexudus floorplanlayoutassets update <id> --name "New Name" --agent` | Update floorplanlayoutasset |
| `nexudus floorplanlayoutassets delete <id> --yes --agent` | Delete floorplanlayoutasset (no prompt) |

#### FloorPlanLayoutAsset list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long |  |
| `--area-unique-id` | string |  |
| `--asset-type` | string |  |
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
| `--floor-offset` | int |  |
| `--from-floor-offset` | range | |
| `--to-floor-offset` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutAsset create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required |  |
| `--area-unique-id` | string |  |
| `--asset-type` | string |  |
| `--angle` | decimal, required |  |
| `--height` | int, required |  |
| `--length` | int, required |  |
| `--width` | int, required |  |
| `--pos-x` | int, required |  |
| `--pos-y` | int, required |  |
| `--floor-offset` | int, required |  |

#### FloorPlanLayoutAsset update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long |  |
| `--area-unique-id` | string |  |
| `--asset-type` | string |  |
| `--angle` | decimal |  |
| `--height` | int |  |
| `--length` | int |  |
| `--width` | int |  |
| `--pos-x` | int |  |
| `--pos-y` | int |  |
| `--floor-offset` | int |  |

<!-- END:GENERATED entity=FloorPlanLayoutAssets -->
