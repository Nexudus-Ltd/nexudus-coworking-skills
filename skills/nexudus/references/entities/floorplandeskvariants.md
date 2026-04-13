# FloorPlanDeskVariants

<!-- BEGIN:GENERATED entity=FloorPlanDeskVariants -->

FloorPlanDeskVariants support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplandeskvariants list --agent` | List all floorplandeskvariants |
| `nexudus floorplandeskvariants list --id <id> --agent` | Filter by single ID |
| `nexudus floorplandeskvariants list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplandeskvariants list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplandeskvariants list --floor-plan-desk-id <value> --coworker-id <value> --agent` | Filter floorplandeskvariants by properties |
| `nexudus floorplandeskvariants list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplandeskvariants get <id> --agent` | Get single floorplandeskvariant |
| `nexudus floorplandeskvariants create --floor-plan-desk-id <value> --name <value> --occupancy-percentage <value> --agent` | Create floorplandeskvariant |
| `nexudus floorplandeskvariants update <id> --name "New Name" --agent` | Update floorplandeskvariant |
| `nexudus floorplandeskvariants delete <id> --yes --agent` | Delete floorplandeskvariant (no prompt) |

#### FloorPlanDeskVariant list filter options

`--floor-plan-desk-id` (long), `--coworker-id` (long), `--name`, `--size` (decimal), `--from-size` (range), `--to-size` (range), `--capacity` (decimal), `--from-capacity` (range), `--to-capacity` (range), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--occupancy-percentage` (decimal), `--from-occupancy-percentage` (range), `--to-occupancy-percentage` (range), `--notes`, `--available-monday` (bool), `--available-tuesday` (bool), `--available-wednesday` (bool), `--available-thursday` (bool), `--available-friday` (bool), `--available-saturday` (bool), `--available-sunday` (bool), `--access-control-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time` (DateTime), `--from-available-from-time` (range), `--to-available-from-time` (range), `--available-to-time` (DateTime), `--from-available-to-time` (range), `--to-available-to-time` (range), `--available-from-time-local` (DateTime), `--from-available-from-time-local` (range), `--to-available-from-time-local` (range), `--available-to-time-local` (DateTime), `--from-available-to-time-local` (range), `--to-available-to-time-local` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### FloorPlanDeskVariant create options

`--floor-plan-desk-id` (long, required), `--coworker-id` (long), `--name` (required), `--size` (decimal), `--capacity` (decimal), `--price` (decimal), `--occupancy-percentage` (decimal, required), `--notes`, `--available-monday` (bool), `--available-tuesday` (bool), `--available-wednesday` (bool), `--available-thursday` (bool), `--available-friday` (bool), `--available-saturday` (bool), `--available-sunday` (bool), `--access-control-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time` (DateTime), `--available-to-time` (DateTime), `--available-from-time-local` (DateTime), `--available-to-time-local` (DateTime)

#### FloorPlanDeskVariant update options

`--floor-plan-desk-id` (long), `--coworker-id` (long), `--name`, `--size` (decimal), `--capacity` (decimal), `--price` (decimal), `--occupancy-percentage` (decimal), `--notes`, `--available-monday` (bool), `--available-tuesday` (bool), `--available-wednesday` (bool), `--available-thursday` (bool), `--available-friday` (bool), `--available-saturday` (bool), `--available-sunday` (bool), `--access-control-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time` (DateTime), `--available-to-time` (DateTime), `--available-from-time-local` (DateTime), `--available-to-time-local` (DateTime)

<!-- END:GENERATED entity=FloorPlanDeskVariants -->
