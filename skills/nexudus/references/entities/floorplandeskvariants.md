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

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--name` | string |  |
| `--size` | decimal |  |
| `--from-size` | range | |
| `--to-size` | range | |
| `--capacity` | decimal |  |
| `--from-capacity` | range | |
| `--to-capacity` | range | |
| `--price` | decimal |  |
| `--from-price` | range | |
| `--to-price` | range | |
| `--occupancy-percentage` | decimal |  |
| `--from-occupancy-percentage` | range | |
| `--to-occupancy-percentage` | range | |
| `--notes` | string |  |
| `--available-monday` | bool |  |
| `--available-tuesday` | bool |  |
| `--available-wednesday` | bool |  |
| `--available-thursday` | bool |  |
| `--available-friday` | bool |  |
| `--available-saturday` | bool |  |
| `--available-sunday` | bool |  |
| `--access-control-group-id` | string |  |
| `--coworker-contract-ids` | string |  |
| `--coworker-contract-full-names` | string |  |
| `--coworker-contract-start-dates` | string |  |
| `--available-from-time` | DateTime |  |
| `--from-available-from-time` | range | |
| `--to-available-from-time` | range | |
| `--available-to-time` | DateTime |  |
| `--from-available-to-time` | range | |
| `--to-available-to-time` | range | |
| `--available-from-time-local` | DateTime |  |
| `--from-available-from-time-local` | range | |
| `--to-available-from-time-local` | range | |
| `--available-to-time-local` | DateTime |  |
| `--from-available-to-time-local` | range | |
| `--to-available-to-time-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanDeskVariant create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long, required |  |
| `--coworker-id` | long |  |
| `--name` | string, required |  |
| `--size` | decimal |  |
| `--capacity` | decimal |  |
| `--price` | decimal |  |
| `--occupancy-percentage` | decimal, required |  |
| `--notes` | string |  |
| `--available-monday` | bool |  |
| `--available-tuesday` | bool |  |
| `--available-wednesday` | bool |  |
| `--available-thursday` | bool |  |
| `--available-friday` | bool |  |
| `--available-saturday` | bool |  |
| `--available-sunday` | bool |  |
| `--access-control-group-id` | string |  |
| `--coworker-contract-ids` | string |  |
| `--coworker-contract-full-names` | string |  |
| `--coworker-contract-start-dates` | string |  |
| `--available-from-time` | DateTime |  |
| `--available-to-time` | DateTime |  |
| `--available-from-time-local` | DateTime |  |
| `--available-to-time-local` | DateTime |  |

#### FloorPlanDeskVariant update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long |  |
| `--coworker-id` | long |  |
| `--name` | string |  |
| `--size` | decimal |  |
| `--capacity` | decimal |  |
| `--price` | decimal |  |
| `--occupancy-percentage` | decimal |  |
| `--notes` | string |  |
| `--available-monday` | bool |  |
| `--available-tuesday` | bool |  |
| `--available-wednesday` | bool |  |
| `--available-thursday` | bool |  |
| `--available-friday` | bool |  |
| `--available-saturday` | bool |  |
| `--available-sunday` | bool |  |
| `--access-control-group-id` | string |  |
| `--coworker-contract-ids` | string |  |
| `--coworker-contract-full-names` | string |  |
| `--coworker-contract-start-dates` | string |  |
| `--available-from-time` | DateTime |  |
| `--available-to-time` | DateTime |  |
| `--available-from-time-local` | DateTime |  |
| `--available-to-time-local` | DateTime |  |

#### FloorPlanDeskVariant PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |
| `--coworker-contract-full-names` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus floorplandeskvariants update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=FloorPlanDeskVariants -->
