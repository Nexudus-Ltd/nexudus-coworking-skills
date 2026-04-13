# FloorPlanLayouts

<!-- BEGIN:GENERATED entity=FloorPlanLayouts -->

FloorPlanLayouts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplanlayouts list --agent` | List all floorplanlayouts |
| `nexudus floorplanlayouts list --id <id> --agent` | Filter by single ID |
| `nexudus floorplanlayouts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplanlayouts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplanlayouts list --business-id <value> --name <value> --agent` | Filter floorplanlayouts by properties |
| `nexudus floorplanlayouts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplanlayouts get <id> --agent` | Get single floorplanlayout |
| `nexudus floorplanlayouts create --business-id <value> --name <value> --size <value> --background-image-scale <value> --tracing-image-scale <value> --floor-level <value> --agent` | Create floorplanlayout |
| `nexudus floorplanlayouts update <id> --name "New Name" --agent` | Update floorplanlayout |
| `nexudus floorplanlayouts delete <id> --yes --agent` | Delete floorplanlayout (no prompt) |

#### FloorPlanLayout list filter options

`--business-id` (long), `--name`, `--new-background-image-url`, `--clear-background-image-file` (bool), `--size` (decimal), `--from-size` (range), `--to-size` (range), `--new-tracing-image-url`, `--clear-tracing-image-file` (bool), `--new-preview-image-url`, `--clear-preview-image-file` (bool), `--background-image-scale` (int), `--from-background-image-scale` (range), `--to-background-image-scale` (range), `--tracing-image-scale` (int), `--from-tracing-image-scale` (range), `--to-tracing-image-scale` (range), `--floor-level` (int), `--from-floor-level` (range), `--to-floor-level` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanLayout create options

`--business-id` (long, required), `--name` (required), `--new-background-image-url`, `--clear-background-image-file` (bool), `--size` (decimal, required), `--new-tracing-image-url`, `--clear-tracing-image-file` (bool), `--new-preview-image-url`, `--clear-preview-image-file` (bool), `--background-image-scale` (int, required), `--tracing-image-scale` (int, required), `--floor-level` (int, required)

#### FloorPlanLayout update options

`--business-id` (long), `--name`, `--new-background-image-url`, `--clear-background-image-file` (bool), `--size` (decimal), `--new-tracing-image-url`, `--clear-tracing-image-file` (bool), `--new-preview-image-url`, `--clear-preview-image-file` (bool), `--background-image-scale` (int), `--tracing-image-scale` (int), `--floor-level` (int)

<!-- END:GENERATED entity=FloorPlanLayouts -->
