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

`--floor-plan-layout-id`, `--area-unique-id`, `--asset-type`, `--angle`, `--from-angle` (range), `--to-angle` (range), `--height`, `--from-height` (range), `--to-height` (range), `--length`, `--from-length` (range), `--to-length` (range), `--width`, `--from-width` (range), `--to-width` (range), `--pos-x`, `--from-pos-x` (range), `--to-pos-x` (range), `--pos-y`, `--from-pos-y` (range), `--to-pos-y` (range), `--floor-offset`, `--from-floor-offset` (range), `--to-floor-offset` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanLayoutAsset create options

`--floor-plan-layout-id` (required), `--area-unique-id`, `--asset-type`, `--angle` (required), `--height` (required), `--length` (required), `--width` (required), `--pos-x` (required), `--pos-y` (required), `--floor-offset` (required)

#### FloorPlanLayoutAsset update options

`--floor-plan-layout-id`, `--area-unique-id`, `--asset-type`, `--angle`, `--height`, `--length`, `--width`, `--pos-x`, `--pos-y`, `--floor-offset`

<!-- END:GENERATED entity=FloorPlanLayoutAssets -->
