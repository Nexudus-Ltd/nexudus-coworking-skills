# FloorPlanAssets

<!-- BEGIN:GENERATED entity=FloorPlanAssets -->

FloorPlanAssets support Search, Get (no Create or Delete via API).

| Command | Description |
| --- | --- |
| `nexudus floorplanassets list --agent` | List all floorplanassets |
| `nexudus floorplanassets list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanassets list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanassets list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanassets list --name <value> --categories <value> --agent` | Filter floorplanassets by properties |
| `nexudus floorplanassets list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanassets get <id> --agent` | Get single floorplanasset |

#### FloorPlanAsset list filter options

`--name`, `--categories`, `--subcategories`, `--tags`, `--materials`, `--description`, `--images2-d`, `--images3-d`, `--images-preview`, `--published` (bool), `--hit-box`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

<!-- END:GENERATED entity=FloorPlanAssets -->
