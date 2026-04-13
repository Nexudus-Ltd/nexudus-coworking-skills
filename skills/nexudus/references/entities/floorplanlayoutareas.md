# FloorPlanLayoutAreas

<!-- BEGIN:GENERATED entity=FloorPlanLayoutAreas -->

FloorPlanLayoutAreas support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayoutareas list --agent` | List all floorplanlayoutareas |
| `nexudus floorplanlayoutareas list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayoutareas list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayoutareas list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayoutareas list --floor-plan-layout-id <value> --name <value> --agent` | Filter floorplanlayoutareas by properties |
| `nexudus floorplanlayoutareas list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayoutareas get <id> --agent` | Get single floorplanlayoutarea |
| `nexudus floorplanlayoutareas create --floor-plan-layout-id <value> --name <value> --size <value> --agent` | Create floorplanlayoutarea |
| `nexudus floorplanlayoutareas update <id> --name "New Name" --agent` | Update floorplanlayoutarea |
| `nexudus floorplanlayoutareas delete <id> --yes --agent` | Delete floorplanlayoutarea (no prompt) |

#### FloorPlanLayoutArea list filter options

`--floor-plan-layout-id` (long), `--name`, `--contained-areas`, `--nodes`, `--size` (decimal), `--from-size` (range), `--to-size` (range), `--color`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanLayoutArea create options

`--floor-plan-layout-id` (long, required), `--name` (required), `--contained-areas`, `--nodes`, `--size` (decimal, required), `--color`

#### FloorPlanLayoutArea update options

`--floor-plan-layout-id` (long), `--name`, `--contained-areas`, `--nodes`, `--size` (decimal), `--color`

<!-- END:GENERATED entity=FloorPlanLayoutAreas -->
