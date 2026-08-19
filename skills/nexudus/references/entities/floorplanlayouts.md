# FloorPlanLayouts

<!-- BEGIN:GENERATED entity=FloorPlanLayouts -->

A **FloorPlanLayout** represents the overall layout configuration of a floor plan, including its dimensions, background image, and visual settings. Each floor plan can have one or more layouts to represent different configurations of the same space.

FloorPlanLayouts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayouts list --agent` | List all floorplanlayouts |
| `nexudus floorplanlayouts list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayouts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayouts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayouts list --business-id <value> --business-name <value> --agent` | Filter floorplanlayouts by properties |
| `nexudus floorplanlayouts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayouts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplanlayouts get <id> --agent` | Get single floorplanlayout |
| `nexudus floorplanlayouts create --business-id <value> --name <value> --size <value> --background-image-scale <value> --tracing-image-scale <value> --floor-level <value> --agent` | Create floorplanlayout |
| `nexudus floorplanlayouts update <id> --name "New Name" --agent` | Update floorplanlayout |
| `nexudus floorplanlayouts delete <id> --yes --agent` | Delete floorplanlayout (no prompt) |

#### FloorPlanLayout list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--business-name` | string | Display name of the linked business (read-only) |
| `--business-currency-code` | string | The business currency code value for this floor plan layout |
| `--name` | string | The name value for this floor plan layout |
| `--background-image-file-name` | string | Current file name of the background image (read-only; upload via the corresponding URL field) |
| `--new-background-image-url` | string | URL of a new file to upload as the background image |
| `--clear-background-image-file` | bool | Set to true to remove the current background image file |
| `--size` | decimal | The size value for this floor plan layout |
| `--from-size` | range | |
| `--to-size` | range | |
| `--tracing-image-file-name` | string | Current file name of the tracing image (read-only; upload via the corresponding URL field) |
| `--new-tracing-image-url` | string | URL of a new file to upload as the tracing image |
| `--clear-tracing-image-file` | bool | Set to true to remove the current tracing image file |
| `--preview-image-file-name` | string | Current file name of the preview image (read-only; upload via the corresponding URL field) |
| `--new-preview-image-url` | string | URL of a new file to upload as the preview image |
| `--clear-preview-image-file` | bool | Set to true to remove the current preview image file |
| `--background-image-scale` | int | The background image scale value for this floor plan layout |
| `--from-background-image-scale` | range | |
| `--to-background-image-scale` | range | |
| `--tracing-image-scale` | int | The tracing image scale value for this floor plan layout |
| `--from-tracing-image-scale` | range | |
| `--to-tracing-image-scale` | range | |
| `--floor-level` | int | The floor level value for this floor plan layout |
| `--from-floor-level` | range | |
| `--to-floor-level` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayout sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlanLayout create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this floor plan layout |
| `--new-background-image-url` | string | URL of a new file to upload as the background image |
| `--clear-background-image-file` | bool | Set to true to remove the current background image file |
| `--size` | decimal, required | The size value for this floor plan layout |
| `--new-tracing-image-url` | string | URL of a new file to upload as the tracing image |
| `--clear-tracing-image-file` | bool | Set to true to remove the current tracing image file |
| `--new-preview-image-url` | string | URL of a new file to upload as the preview image |
| `--clear-preview-image-file` | bool | Set to true to remove the current preview image file |
| `--background-image-scale` | int, required | The background image scale value for this floor plan layout |
| `--tracing-image-scale` | int, required | The tracing image scale value for this floor plan layout |
| `--floor-level` | int, required | The floor level value for this floor plan layout |

#### FloorPlanLayout update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this floor plan layout |
| `--new-background-image-url` | string | URL of a new file to upload as the background image |
| `--clear-background-image-file` | bool | Set to true to remove the current background image file |
| `--size` | decimal | The size value for this floor plan layout |
| `--new-tracing-image-url` | string | URL of a new file to upload as the tracing image |
| `--clear-tracing-image-file` | bool | Set to true to remove the current tracing image file |
| `--new-preview-image-url` | string | URL of a new file to upload as the preview image |
| `--clear-preview-image-file` | bool | Set to true to remove the current preview image file |
| `--background-image-scale` | int | The background image scale value for this floor plan layout |
| `--tracing-image-scale` | int | The tracing image scale value for this floor plan layout |
| `--floor-level` | int | The floor level value for this floor plan layout |

<!-- END:GENERATED entity=FloorPlanLayouts -->
