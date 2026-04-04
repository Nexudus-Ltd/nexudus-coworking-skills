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

`--business-id`, `--name`, `--new-background-image-url`, `--clear-background-image`, `--size`, `--new-tracing-image-url`, `--clear-tracing-image`, `--new-preview-image-url`, `--clear-preview-image`, `--background-image-scale`, `--tracing-image-scale`, `--floor-level`

#### FloorPlanLayout create options

`--business-id` (required), `--name` (required), `--new-background-image-url`, `--clear-background-image`, `--size` (required), `--areas` (list, repeat flag), `--added-areas` (list, repeat flag), `--removed-areas` (list, repeat flag), `--assets` (list, repeat flag), `--added-assets` (list, repeat flag), `--removed-assets` (list, repeat flag), `--floorplan-transitions` (list, repeat flag), `--added-floorplan-transitions` (list, repeat flag), `--removed-floorplan-transitions` (list, repeat flag), `--edges` (list, repeat flag), `--added-edges` (list, repeat flag), `--removed-edges` (list, repeat flag), `--nodes` (list, repeat flag), `--added-nodes` (list, repeat flag), `--removed-nodes` (list, repeat flag), `--new-tracing-image-url`, `--clear-tracing-image`, `--new-preview-image-url`, `--clear-preview-image`, `--background-image-scale` (required), `--tracing-image-scale` (required), `--floor-level` (required)

#### FloorPlanLayout update options

`--business-id`, `--name`, `--new-background-image-url`, `--clear-background-image`, `--size`, `--areas` (list, repeat flag), `--added-areas` (list, repeat flag), `--removed-areas` (list, repeat flag), `--assets` (list, repeat flag), `--added-assets` (list, repeat flag), `--removed-assets` (list, repeat flag), `--floorplan-transitions` (list, repeat flag), `--added-floorplan-transitions` (list, repeat flag), `--removed-floorplan-transitions` (list, repeat flag), `--edges` (list, repeat flag), `--added-edges` (list, repeat flag), `--removed-edges` (list, repeat flag), `--nodes` (list, repeat flag), `--added-nodes` (list, repeat flag), `--removed-nodes` (list, repeat flag), `--new-tracing-image-url`, `--clear-tracing-image`, `--new-preview-image-url`, `--clear-preview-image`, `--background-image-scale`, `--tracing-image-scale`, `--floor-level`

**List properties (only returned by `get`, not by `list`):** `Areas`, `AddedAreas`, `RemovedAreas`, `Assets`, `AddedAssets`, `RemovedAssets`, `FloorplanTransitions`, `AddedFloorplanTransitions`, `RemovedFloorplanTransitions`, `Edges`, `AddedEdges`, `RemovedEdges`, `Nodes`, `AddedNodes`, `RemovedNodes`

<!-- END:GENERATED entity=FloorPlanLayouts -->
