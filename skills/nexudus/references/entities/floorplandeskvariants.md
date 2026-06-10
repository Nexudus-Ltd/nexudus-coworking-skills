# FloorPlanDeskVariants

<!-- BEGIN:GENERATED entity=FloorPlanDeskVariants -->

A **FloorPlanDeskVariant** defines an alternative visual representation or configuration for a desk on a floor plan. Variants allow the same desk to be displayed differently based on context or state.

FloorPlanDeskVariants support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplandeskvariants list --agent` | List all floorplandeskvariants |
| `nexudus floorplandeskvariants list --id <id> --agent` | Filter by single ID |
| `nexudus floorplandeskvariants list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplandeskvariants list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplandeskvariants list --floor-plan-desk-id <value> --coworker-id <value> --agent` | Filter floorplandeskvariants by properties |
| `nexudus floorplandeskvariants list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplandeskvariants list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplandeskvariants get <id> --agent` | Get single floorplandeskvariant |
| `nexudus floorplandeskvariants create --floor-plan-desk-id <value> --name <value> --occupancy-percentage <value> --agent` | Create floorplandeskvariant |
| `nexudus floorplandeskvariants update <id> --name "New Name" --agent` | Update floorplandeskvariant |
| `nexudus floorplandeskvariants delete <id> --yes --agent` | Delete floorplandeskvariant (no prompt) |

#### FloorPlanDeskVariant list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--name` | string | The name value for this floor plan desk variant |
| `--size` | decimal | The size value for this floor plan desk variant |
| `--from-size` | range | |
| `--to-size` | range | |
| `--capacity` | decimal | The capacity value for this floor plan desk variant |
| `--from-capacity` | range | |
| `--to-capacity` | range | |
| `--price` | decimal | Unit price amount |
| `--from-price` | range | |
| `--to-price` | range | |
| `--occupancy-percentage` | decimal | The occupancy percentage value for this floor plan desk variant |
| `--from-occupancy-percentage` | range | |
| `--to-occupancy-percentage` | range | |
| `--notes` | string | Optional notes or comments about this floor plan desk variant |
| `--available-monday` | bool | Whether available monday is enabled |
| `--available-tuesday` | bool | Whether available tuesday is enabled |
| `--available-wednesday` | bool | Whether available wednesday is enabled |
| `--available-thursday` | bool | Whether available thursday is enabled |
| `--available-friday` | bool | Whether available friday is enabled |
| `--available-saturday` | bool | Whether available saturday is enabled |
| `--available-sunday` | bool | Whether available sunday is enabled |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--coworker-contract-ids` | string | The coworker contract ids value for this floor plan desk variant |
| `--coworker-contract-full-names` | string | The coworker contract full names value for this floor plan desk variant |
| `--coworker-contract-start-dates` | string | The coworker contract start dates value for this floor plan desk variant |
| `--available-from-time` | DateTime | Date/time value for available from time |
| `--from-available-from-time` | range | |
| `--to-available-from-time` | range | |
| `--available-to-time` | DateTime | Date/time value for available to time |
| `--from-available-to-time` | range | |
| `--to-available-to-time` | range | |
| `--available-from-time-local` | DateTime | Date/time value for available from time local |
| `--from-available-from-time-local` | range | |
| `--to-available-from-time-local` | range | |
| `--available-to-time-local` | DateTime | Date/time value for available to time local |
| `--from-available-to-time-local` | range | |
| `--to-available-to-time-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### FloorPlanDeskVariant sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### FloorPlanDeskVariant create options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long, required | ID of the floor plan desk linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--name` | string, required | The name value for this floor plan desk variant |
| `--size` | decimal | The size value for this floor plan desk variant |
| `--capacity` | decimal | The capacity value for this floor plan desk variant |
| `--price` | decimal | Unit price amount |
| `--occupancy-percentage` | decimal, required | The occupancy percentage value for this floor plan desk variant |
| `--notes` | string | Optional notes or comments about this floor plan desk variant |
| `--available-monday` | bool | Whether available monday is enabled |
| `--available-tuesday` | bool | Whether available tuesday is enabled |
| `--available-wednesday` | bool | Whether available wednesday is enabled |
| `--available-thursday` | bool | Whether available thursday is enabled |
| `--available-friday` | bool | Whether available friday is enabled |
| `--available-saturday` | bool | Whether available saturday is enabled |
| `--available-sunday` | bool | Whether available sunday is enabled |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--coworker-contract-ids` | string | The coworker contract ids value for this floor plan desk variant |
| `--coworker-contract-full-names` | string | The coworker contract full names value for this floor plan desk variant |
| `--coworker-contract-start-dates` | string | The coworker contract start dates value for this floor plan desk variant |
| `--available-from-time` | DateTime | Date/time value for available from time |
| `--available-to-time` | DateTime | Date/time value for available to time |
| `--available-from-time-local` | DateTime | Date/time value for available from time local |
| `--available-to-time-local` | DateTime | Date/time value for available to time local |

#### FloorPlanDeskVariant update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long | ID of the floor plan desk linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--name` | string | The name value for this floor plan desk variant |
| `--size` | decimal | The size value for this floor plan desk variant |
| `--capacity` | decimal | The capacity value for this floor plan desk variant |
| `--price` | decimal | Unit price amount |
| `--occupancy-percentage` | decimal | The occupancy percentage value for this floor plan desk variant |
| `--notes` | string | Optional notes or comments about this floor plan desk variant |
| `--available-monday` | bool | Whether available monday is enabled |
| `--available-tuesday` | bool | Whether available tuesday is enabled |
| `--available-wednesday` | bool | Whether available wednesday is enabled |
| `--available-thursday` | bool | Whether available thursday is enabled |
| `--available-friday` | bool | Whether available friday is enabled |
| `--available-saturday` | bool | Whether available saturday is enabled |
| `--available-sunday` | bool | Whether available sunday is enabled |
| `--access-control-group-id` | string | ID of the access control group associated with this record |
| `--coworker-contract-ids` | string | The coworker contract ids value for this floor plan desk variant |
| `--coworker-contract-full-names` | string | The coworker contract full names value for this floor plan desk variant |
| `--coworker-contract-start-dates` | string | The coworker contract start dates value for this floor plan desk variant |
| `--available-from-time` | DateTime | Date/time value for available from time |
| `--available-to-time` | DateTime | Date/time value for available to time |
| `--available-from-time-local` | DateTime | Date/time value for available from time local |
| `--available-to-time-local` | DateTime | Date/time value for available to time local |

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
