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

| Option | Type | Description |
| --- | --- | --- |
| `--name` | string |  |
| `--categories` | string |  |
| `--subcategories` | string |  |
| `--tags` | string |  |
| `--materials` | string |  |
| `--description` | string |  |
| `--images2-d` | string |  |
| `--images3-d` | string |  |
| `--images-preview` | string |  |
| `--published` | bool |  |
| `--hit-box` | string |  |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

<!-- END:GENERATED entity=FloorPlanAssets -->
