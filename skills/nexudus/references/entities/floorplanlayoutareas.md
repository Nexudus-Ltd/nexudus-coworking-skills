# FloorPlanLayoutAreas

<!-- BEGIN:GENERATED entity=FloorPlanLayoutAreas -->

A **FloorPlanLayoutArea** defines a named region within a floor plan layout, such as a zone, room, or section. Areas help organize and group desks and assets within the floor plan.

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

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--name` | string | The name value for this floor plan layout area |
| `--contained-areas` | string | The contained areas value for this floor plan layout area |
| `--nodes` | string | The nodes value for this floor plan layout area |
| `--size` | decimal | The size value for this floor plan layout area |
| `--from-size` | range | |
| `--to-size` | range | |
| `--color` | string | The color value for this floor plan layout area |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanLayoutArea create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long, required | ID of the floor plan layout linked to this record |
| `--name` | string, required | The name value for this floor plan layout area |
| `--contained-areas` | string | The contained areas value for this floor plan layout area |
| `--nodes` | string | The nodes value for this floor plan layout area |
| `--size` | decimal, required | The size value for this floor plan layout area |
| `--color` | string | The color value for this floor plan layout area |

#### FloorPlanLayoutArea update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-layout-id` | long | ID of the floor plan layout linked to this record |
| `--name` | string | The name value for this floor plan layout area |
| `--contained-areas` | string | The contained areas value for this floor plan layout area |
| `--nodes` | string | The nodes value for this floor plan layout area |
| `--size` | decimal | The size value for this floor plan layout area |
| `--color` | string | The color value for this floor plan layout area |

<!-- END:GENERATED entity=FloorPlanLayoutAreas -->
