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

`--business-id` (long), `--floor-plan-layout-id` (long), `--name`, `--new-background-image-url`, `--clear-background-image-file` (bool), `--display-background` (bool), `--background-scale` (int), `--from-background-scale` (range), `--to-background-scale` (range), `--position-x` (int), `--from-position-x` (range), `--to-position-x` (range), `--position-y` (int), `--from-position-y` (range), `--to-position-y` (range), `--floor-level` (int), `--from-floor-level` (range), `--to-floor-level` (range), `--scale` (decimal), `--from-scale` (range), `--to-scale` (range), `--capacity` (int), `--from-capacity` (range), `--to-capacity` (range), `--archilogic-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlan create options

`--business-id` (long, required), `--floor-plan-layout-id` (long), `--name` (required), `--new-background-image-url`, `--clear-background-image-file` (bool), `--display-background` (bool), `--background-scale` (int, required), `--position-x` (int, required), `--position-y` (int, required), `--floor-level` (int, required), `--scale` (decimal, required), `--capacity` (int), `--archilogic-unique-id`

#### FloorPlan update options

`--business-id` (long), `--floor-plan-layout-id` (long), `--name`, `--new-background-image-url`, `--clear-background-image-file` (bool), `--display-background` (bool), `--background-scale` (int), `--position-x` (int), `--position-y` (int), `--floor-level` (int), `--scale` (decimal), `--capacity` (int), `--archilogic-unique-id`

### FloorPlan (key fields)

`Id`, `BusinessName`, `FloorPlanLayoutName`, `Name`

<!-- END:GENERATED entity=FloorPlans -->
