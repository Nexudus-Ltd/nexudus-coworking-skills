# FloorPlans

<!-- BEGIN:GENERATED entity=FloorPlans -->

FloorPlans support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplans list --agent` | List all floorplans |
| `nexudus floorplans list --id <id> --agent` | Filter by single ID |
| `nexudus floorplans list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplans list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplans list --business-id <value> --floor-plan-layout-id <value> --agent` | Filter floorplans by properties |
| `nexudus floorplans list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplans get <id> --agent` | Get single floorplan |
| `nexudus floorplans create --business-id <value> --name <value> --background-scale <value> --position-x <value> --position-y <value> --floor-level <value> --scale <value> --agent` | Create floorplan |
| `nexudus floorplans update <id> --name "New Name" --agent` | Update floorplan |
| `nexudus floorplans delete <id> --yes --agent` | Delete floorplan (no prompt) |

#### FloorPlan list filter options

`--business-id`, `--floor-plan-layout-id`, `--name`, `--new-background-image-url`, `--clear-background-image-file`, `--display-background`, `--background-scale`, `--from-background-scale` (range), `--to-background-scale` (range), `--position-x`, `--from-position-x` (range), `--to-position-x` (range), `--position-y`, `--from-position-y` (range), `--to-position-y` (range), `--floor-level`, `--from-floor-level` (range), `--to-floor-level` (range), `--scale`, `--from-scale` (range), `--to-scale` (range), `--capacity`, `--from-capacity` (range), `--to-capacity` (range), `--archilogic-unique-id`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlan create options

`--business-id` (required), `--floor-plan-layout-id`, `--name` (required), `--new-background-image-url`, `--clear-background-image-file`, `--display-background`, `--background-scale` (required), `--position-x` (required), `--position-y` (required), `--floor-level` (required), `--scale` (required), `--capacity`, `--archilogic-unique-id`

#### FloorPlan update options

`--business-id`, `--floor-plan-layout-id`, `--name`, `--new-background-image-url`, `--clear-background-image-file`, `--display-background`, `--background-scale`, `--position-x`, `--position-y`, `--floor-level`, `--scale`, `--capacity`, `--archilogic-unique-id`

<!-- END:GENERATED entity=FloorPlans -->
