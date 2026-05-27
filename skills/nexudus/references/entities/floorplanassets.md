# FloorPlanAssets

<!-- BEGIN:GENERATED entity=FloorPlanAssets -->

A **FloorPlanAsset** represents a physical asset (such as furniture, equipment, or decoration) placed on a floor plan. Assets are visual elements that help represent the physical layout of a space.

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
| `--name` | string | The name value for this floor plan asset |
| `--categories` | string | The categories value for this floor plan asset |
| `--subcategories` | string | The subcategories value for this floor plan asset |
| `--tags` | string | Comma-separated tags for categorising and filtering |
| `--materials` | string | The materials value for this floor plan asset |
| `--description` | string | Free-text description of this floor plan asset |
| `--images2-d` | string | The images2 d value for this floor plan asset |
| `--images3-d` | string | The images3 d value for this floor plan asset |
| `--images-preview` | string | The images preview value for this floor plan asset |
| `--published` | bool | Whether published is enabled |
| `--hit-box` | string | The hit box value for this floor plan asset |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

<!-- END:GENERATED entity=FloorPlanAssets -->
