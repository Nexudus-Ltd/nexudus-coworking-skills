# FloorPlans

<!-- BEGIN:GENERATED entity=FloorPlans -->

A floor plan represents one floor at a location and groups the bookable or assignable floor plan units shown through an uploaded image, a Nexudus Floor Plan Editor layout, or an Archilogic 3D scene.

FloorPlans support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplans list --agent` | List all floorplans |
| `nexudus floorplans list --id <id> --agent` | Filter by single ID |
| `nexudus floorplans list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplans list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplans list --business-name <value> --floor-plan-layout-name <value> --agent` | Filter floorplans by properties |
| `nexudus floorplans list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplans list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplans get <id> --agent` | Get single floorplan |
| `nexudus floorplans create --business-id <value> --name <value> --background-scale <value> --agent` | Create floorplan |
| `nexudus floorplans update <id> --name "New Name" --agent` | Update floorplan |
| `nexudus floorplans delete <id> --yes --agent` | Delete floorplan (no prompt) |

#### FloorPlan list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the required location that owns this floor plan |
| `--business-name` | string | Location name |
| `--business-currency-code` | string | Currency code of the location |
| `--floor-plan-layout-id` | long | ID of the optional Nexudus Floor Plan Editor layout associated with this floor plan; the layout must belong to a location the user can access |
| `--floor-plan-layout-name` | string | Floor plan layout name |
| `--name` | string | Required display name; changing it also updates the associated editor layout name and floor plan unit names containing the previous name |
| `--background-image-file-name` | string | Filename of the currently stored background/tracing image |
| `--new-background-image-url` | string | URL of a new background/tracing image to upload. The image will be fetched and stored when the floor plan is saved |
| `--clear-background-image-file` | bool | Set to true to remove the current background/tracing image from this floor plan |
| `--display-background` | bool | Whether the uploaded background image is displayed for an image-based floor plan |
| `--background-scale` | int | Integer percentage used to scale floor plan unit coordinates over the background image; 100 is full scale, values above 100 are capped at 100 when rendered, and non-positive values render at 33 |
| `--from-background-scale` | range | |
| `--to-background-scale` | range | |
| `--capacity` | int | Optional maximum number of simultaneous bookings accepted across this floor plan; null means unlimited |
| `--from-capacity` | range | |
| `--to-capacity` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlan sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlan create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the required location that owns this floor plan |
| `--floor-plan-layout-id` | long | ID of the optional Nexudus Floor Plan Editor layout associated with this floor plan; the layout must belong to a location the user can access |
| `--name` | string, required | Required display name; changing it also updates the associated editor layout name and floor plan unit names containing the previous name |
| `--new-background-image-url` | string | URL of a new background/tracing image to upload. The image will be fetched and stored when the floor plan is saved |
| `--clear-background-image-file` | bool | Set to true to remove the current background/tracing image from this floor plan |
| `--display-background` | bool | Whether the uploaded background image is displayed for an image-based floor plan |
| `--background-scale` | int, required | Integer percentage used to scale floor plan unit coordinates over the background image; 100 is full scale, values above 100 are capped at 100 when rendered, and non-positive values render at 33 |
| `--capacity` | int | Optional maximum number of simultaneous bookings accepted across this floor plan; null means unlimited |

#### FloorPlan update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the required location that owns this floor plan |
| `--floor-plan-layout-id` | long | ID of the optional Nexudus Floor Plan Editor layout associated with this floor plan; the layout must belong to a location the user can access |
| `--name` | string | Required display name; changing it also updates the associated editor layout name and floor plan unit names containing the previous name |
| `--new-background-image-url` | string | URL of a new background/tracing image to upload. The image will be fetched and stored when the floor plan is saved |
| `--clear-background-image-file` | bool | Set to true to remove the current background/tracing image from this floor plan |
| `--display-background` | bool | Whether the uploaded background image is displayed for an image-based floor plan |
| `--background-scale` | int | Integer percentage used to scale floor plan unit coordinates over the background image; 100 is full scale, values above 100 are capped at 100 when rendered, and non-positive values render at 33 |
| `--capacity` | int | Optional maximum number of simultaneous bookings accepted across this floor plan; null means unlimited |

### FloorPlan (key fields)

`Id`, `BusinessName`, `FloorPlanLayoutName`, `Name`

<!-- END:GENERATED entity=FloorPlans -->
