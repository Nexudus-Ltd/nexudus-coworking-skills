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

`--floor-plan-desk-id`, `--coworker-id`, `--name`, `--size`, `--capacity`, `--price`, `--occupancy-percentage`, `--notes`, `--available-monday`, `--available-tuesday`, `--available-wednesday`, `--available-thursday`, `--available-friday`, `--available-saturday`, `--available-sunday`, `--access-control-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--available-to-time`, `--available-from-time-local`, `--available-to-time-local`

#### FloorPlanDeskVariant create options

`--floor-plan-desk-id` (required), `--coworker-id`, `--name` (required), `--size`, `--capacity`, `--price`, `--occupancy-percentage` (required), `--notes`, `--available-monday`, `--available-tuesday`, `--available-wednesday`, `--available-thursday`, `--available-friday`, `--available-saturday`, `--available-sunday`, `--access-control-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--available-to-time`, `--available-from-time-local`, `--available-to-time-local`

#### FloorPlanDeskVariant update options

`--floor-plan-desk-id`, `--coworker-id`, `--name`, `--size`, `--capacity`, `--price`, `--occupancy-percentage`, `--notes`, `--available-monday`, `--available-tuesday`, `--available-wednesday`, `--available-thursday`, `--available-friday`, `--available-saturday`, `--available-sunday`, `--access-control-group-id`, `--coworker-contract-ids`, `--coworker-contract-full-names`, `--coworker-contract-start-dates`, `--available-from-time`, `--available-to-time`, `--available-from-time-local`, `--available-to-time-local`

<!-- END:GENERATED entity=FloorPlanDeskVariants -->
