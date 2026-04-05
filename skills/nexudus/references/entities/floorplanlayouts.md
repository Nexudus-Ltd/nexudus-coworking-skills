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

`--business-id`, `--name`, `--new-background-image-url`, `--clear-background-image-file`, `--size`, `--from-size` (range), `--to-size` (range), `--new-tracing-image-url`, `--clear-tracing-image-file`, `--new-preview-image-url`, `--clear-preview-image-file`, `--background-image-scale`, `--from-background-image-scale` (range), `--to-background-image-scale` (range), `--tracing-image-scale`, `--from-tracing-image-scale` (range), `--to-tracing-image-scale` (range), `--floor-level`, `--from-floor-level` (range), `--to-floor-level` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanLayout create options

`--business-id` (required), `--name` (required), `--new-background-image-url`, `--clear-background-image-file`, `--size` (required), `--new-tracing-image-url`, `--clear-tracing-image-file`, `--new-preview-image-url`, `--clear-preview-image-file`, `--background-image-scale` (required), `--tracing-image-scale` (required), `--floor-level` (required)

#### FloorPlanLayout update options

`--business-id`, `--name`, `--new-background-image-url`, `--clear-background-image-file`, `--size`, `--new-tracing-image-url`, `--clear-tracing-image-file`, `--new-preview-image-url`, `--clear-preview-image-file`, `--background-image-scale`, `--tracing-image-scale`, `--floor-level`

<!-- END:GENERATED entity=FloorPlanLayouts -->
