# FloorPlans

<!-- BEGIN:GENERATED entity=FloorPlans -->

A **FloorPlan** is a visual diagram representing a single floor of a location. Floor plans are used by admins and customers to get an overview of the space layout, including rooms, desks, and other areas.

Each floor plan belongs to a location (`Business`) and can optionally reference a `FloorPlanLayout` template. A background/tracing image can be uploaded to overlay the drawn areas, and its position and scale can be adjusted independently from the floor plan's own scale.

Once created, floor plan units (FloorPlanDesks) are added to the floor plan to represent individual bookable or non-bookable areas such as offices, dedicated desks, hot desks, and meeting rooms.

FloorPlans support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplans list --agent` | List all floorplans |
| `nexudus floorplans list --id <id> --agent` | Filter by single ID |
| `nexudus floorplans list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplans list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplans list --name <value> --agent` | Filter floorplans by properties |
| `nexudus floorplans list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplans get <id> --agent` | Get single floorplan |
| `nexudus floorplans create --business-id <value> --name <value> --background-scale <value> --position-x <value> --position-y <value> --floor-level <value> --scale <value> --agent` | Create floorplan |
| `nexudus floorplans update <id> --name "New Name" --agent` | Update floorplan |
| `nexudus floorplans delete <id> --yes --agent` | Delete floorplan (no prompt) |

#### FloorPlan list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this floor plan belongs to |
| `--floor-plan-layout-id` | long | ID of the floor plan layout template to apply to this floor plan |
| `--name` | string | Display name of the floor plan (e.g. 'Ground Floor', 'Level 2') |
| `--new-background-image-url` | string | URL of a new background/tracing image to upload. The image will be fetched and stored when the floor plan is saved |
| `--clear-background-image-file` | bool | Set to true to remove the current background/tracing image from this floor plan |
| `--display-background` | bool | Whether the background/tracing image is visible when the floor plan is rendered |
| `--background-scale` | int | Zoom/scale factor applied to the background/tracing image, expressed as a percentage (e.g. 100 = original size) |
| `--from-background-scale` | range | |
| `--to-background-scale` | range | |
| `--position-x` | int | Horizontal offset (in pixels) of the background image within the floor plan canvas |
| `--from-position-x` | range | |
| `--to-position-x` | range | |
| `--position-y` | int | Vertical offset (in pixels) of the background image within the floor plan canvas |
| `--from-position-y` | range | |
| `--to-position-y` | range | |
| `--floor-level` | int | Floor number used to order floor plans (e.g. 0 = ground floor, 1 = first floor, -1 = basement) |
| `--from-floor-level` | range | |
| `--to-floor-level` | range | |
| `--scale` | decimal | Real-world scale of the floor plan, representing how many real-world units correspond to one canvas unit |
| `--from-scale` | range | |
| `--to-scale` | range | |
| `--capacity` | int | Maximum number of people this floor can accommodate at the same time |
| `--from-capacity` | range | |
| `--to-capacity` | range | |
| `--archilogic-unique-id` | string | Unique identifier used to link this floor plan to a corresponding Archilogic 3D model |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlan create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location this floor plan belongs to |
| `--floor-plan-layout-id` | long | ID of the floor plan layout template to apply to this floor plan |
| `--name` | string, required | Display name of the floor plan (e.g. 'Ground Floor', 'Level 2') |
| `--new-background-image-url` | string | URL of a new background/tracing image to upload. The image will be fetched and stored when the floor plan is saved |
| `--clear-background-image-file` | bool | Set to true to remove the current background/tracing image from this floor plan |
| `--display-background` | bool | Whether the background/tracing image is visible when the floor plan is rendered |
| `--background-scale` | int, required | Zoom/scale factor applied to the background/tracing image, expressed as a percentage (e.g. 100 = original size) |
| `--position-x` | int, required | Horizontal offset (in pixels) of the background image within the floor plan canvas |
| `--position-y` | int, required | Vertical offset (in pixels) of the background image within the floor plan canvas |
| `--floor-level` | int, required | Floor number used to order floor plans (e.g. 0 = ground floor, 1 = first floor, -1 = basement) |
| `--scale` | decimal, required | Real-world scale of the floor plan, representing how many real-world units correspond to one canvas unit |
| `--capacity` | int | Maximum number of people this floor can accommodate at the same time |
| `--archilogic-unique-id` | string | Unique identifier used to link this floor plan to a corresponding Archilogic 3D model |

#### FloorPlan update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location this floor plan belongs to |
| `--floor-plan-layout-id` | long | ID of the floor plan layout template to apply to this floor plan |
| `--name` | string | Display name of the floor plan (e.g. 'Ground Floor', 'Level 2') |
| `--new-background-image-url` | string | URL of a new background/tracing image to upload. The image will be fetched and stored when the floor plan is saved |
| `--clear-background-image-file` | bool | Set to true to remove the current background/tracing image from this floor plan |
| `--display-background` | bool | Whether the background/tracing image is visible when the floor plan is rendered |
| `--background-scale` | int | Zoom/scale factor applied to the background/tracing image, expressed as a percentage (e.g. 100 = original size) |
| `--position-x` | int | Horizontal offset (in pixels) of the background image within the floor plan canvas |
| `--position-y` | int | Vertical offset (in pixels) of the background image within the floor plan canvas |
| `--floor-level` | int | Floor number used to order floor plans (e.g. 0 = ground floor, 1 = first floor, -1 = basement) |
| `--scale` | decimal | Real-world scale of the floor plan, representing how many real-world units correspond to one canvas unit |
| `--capacity` | int | Maximum number of people this floor can accommodate at the same time |
| `--archilogic-unique-id` | string | Unique identifier used to link this floor plan to a corresponding Archilogic 3D model |

### FloorPlan (key fields)

`Id`, `BusinessName`, `FloorPlanLayoutName`, `Name`

<!-- END:GENERATED entity=FloorPlans -->
