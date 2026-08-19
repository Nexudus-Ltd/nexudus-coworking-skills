# FloorPlanDeskVariants

<!-- BEGIN:GENERATED entity=FloorPlanDeskVariants -->

A FloorPlanDeskVariant, called a Package by operators, defines how a location's floor plan unit can be contracted under different availability, setup, or pricing conditions. Packages can split an office between customers on different weekdays, or offer the same unit as a private office (full-time or fractional), storage unit, or event space.

FloorPlanDeskVariants support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus floorplandeskvariants list --agent` | List all floorplandeskvariants |
| `nexudus floorplandeskvariants list --id <id> --agent` | Filter by single ID |
| `nexudus floorplandeskvariants list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus floorplandeskvariants list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus floorplandeskvariants list --floor-plan-desk-id <value> --floor-plan-desk-name <value> --agent` | Filter floorplandeskvariants by properties |
| `nexudus floorplandeskvariants list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus floorplandeskvariants list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus floorplandeskvariants get <id> --agent` | Get single floorplandeskvariant |
| `nexudus floorplandeskvariants create --floor-plan-desk-id <value> --name <value> --occupancy-percentage <value> --agent` | Create floorplandeskvariant |
| `nexudus floorplandeskvariants update <id> --name "New Name" --agent` | Update floorplandeskvariant |
| `nexudus floorplandeskvariants delete <id> --yes --agent` | Delete floorplandeskvariant (no prompt) |

#### FloorPlanDeskVariant list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long | ID of the required floor plan unit this variant configures; the unit determines the owning location |
| `--floor-plan-desk-name` | string | Display name of the linked floor plan desk (read-only) |
| `--floor-plan-desk-price` | decimal | The floor plan desk price value for this floor plan desk variant |
| `--from-floor-plan-desk-price` | range | |
| `--to-floor-plan-desk-price` | range | |
| `--floor-plan-desk-floor-plan-id` | int | ID of the floor plan desk floor plan associated with this record |
| `--from-floor-plan-desk-floor-plan-id` | range | |
| `--to-floor-plan-desk-floor-plan-id` | range | |
| `--floor-plan-desk-floor-plan-name` | string | Display name of the linked floor plan desk floor plan (read-only) |
| `--floor-plan-desk-floor-plan-business-id` | int | ID of the floor plan desk floor plan business associated with this record |
| `--from-floor-plan-desk-floor-plan-business-id` | range | |
| `--to-floor-plan-desk-floor-plan-business-id` | range | |
| `--floor-plan-desk-floor-plan-business-name` | string | Display name of the linked floor plan desk floor plan business (read-only) |
| `--floor-plan-desk-floor-plan-business-currency-code` | string | The floor plan desk floor plan business currency code value for this floor plan desk variant |
| `--coworker-id` | long | ID of the optional customer this variant is associated with |
| `--coworker-full-name` | string | Display name of the linked coworker full (read-only) |
| `--coworker-company-name` | string | Display name of the linked coworker company (read-only) |
| `--coworker-coworker-type` | string | The coworker coworker type value for this floor plan desk variant |
| `--coworker-email` | string | The coworker email value for this floor plan desk variant |
| `--coworker-team-names` | string | The coworker team names value for this floor plan desk variant |
| `--name` | string | Required, non-empty display name for this alternate floor plan unit configuration |
| `--size` | decimal | Optional floor area in square metres for this configuration |
| `--from-size` | range | |
| `--to-size` | range | |
| `--capacity` | decimal | Optional number of seats this configuration can accommodate |
| `--from-capacity` | range | |
| `--to-capacity` | range | |
| `--price` | decimal | Optional target price in the owning location's currency, used for occupancy reporting rather than billing |
| `--from-price` | range | |
| `--to-price` | range | |
| `--occupancy-percentage` | decimal | Percentage of the floor plan unit's total possible use reported when this package is contracted; normally divide use evenly across packages according to the number of weekdays each is available |
| `--from-occupancy-percentage` | range | |
| `--to-occupancy-percentage` | range | |
| `--notes` | string | Optional internal notes about this configuration, limited to 255 characters |
| `--available-monday` | bool | Whether this configuration is marked available on Monday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-tuesday` | bool | Whether this configuration is marked available on Tuesday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-wednesday` | bool | Whether this configuration is marked available on Wednesday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-thursday` | bool | Whether this configuration is marked available on Thursday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-friday` | bool | Whether this configuration is marked available on Friday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-saturday` | bool | Whether this configuration is marked available on Saturday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-sunday` | bool | Whether this configuration is marked available on Sunday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--coworker-contract-ids` | string | Read-only denormalized IDs of contracts linked to this configuration; update the contracts rather than this projection |
| `--coworker-contract-full-names` | string | Read-only denormalized customer names from contracts linked to this configuration; update the contracts rather than this projection |
| `--coworker-contract-start-dates` | string | Read-only denormalized start dates from contracts linked to this configuration; update the contracts rather than this projection |
| `--available-from-time` | DateTime | Optional inclusive UTC start of this configuration's availability window; it must precede AvailableToTime when both are set |
| `--from-available-from-time` | range | |
| `--to-available-from-time` | range | |
| `--available-to-time` | DateTime | Optional inclusive UTC end of this configuration's availability window; null means no end, and it must follow AvailableFromTime when both are set |
| `--from-available-to-time` | range | |
| `--to-available-to-time` | range | |
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
| `--floor-plan-desk-id` | long, required | ID of the required floor plan unit this variant configures; the unit determines the owning location |
| `--coworker-id` | long | ID of the optional customer this variant is associated with |
| `--name` | string, required | Required, non-empty display name for this alternate floor plan unit configuration |
| `--size` | decimal | Optional floor area in square metres for this configuration |
| `--capacity` | decimal | Optional number of seats this configuration can accommodate |
| `--price` | decimal | Optional target price in the owning location's currency, used for occupancy reporting rather than billing |
| `--occupancy-percentage` | decimal, required | Percentage of the floor plan unit's total possible use reported when this package is contracted; normally divide use evenly across packages according to the number of weekdays each is available |
| `--notes` | string | Optional internal notes about this configuration, limited to 255 characters |
| `--available-monday` | bool | Whether this configuration is marked available on Monday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-tuesday` | bool | Whether this configuration is marked available on Tuesday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-wednesday` | bool | Whether this configuration is marked available on Wednesday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-thursday` | bool | Whether this configuration is marked available on Thursday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-friday` | bool | Whether this configuration is marked available on Friday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-saturday` | bool | Whether this configuration is marked available on Saturday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-sunday` | bool | Whether this configuration is marked available on Sunday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-from-time` | DateTime | Optional inclusive UTC start of this configuration's availability window; it must precede AvailableToTime when both are set |
| `--available-to-time` | DateTime | Optional inclusive UTC end of this configuration's availability window; null means no end, and it must follow AvailableFromTime when both are set |

#### FloorPlanDeskVariant update options

| Option | Type | Description |
| --- | --- | --- |
| `--floor-plan-desk-id` | long | ID of the required floor plan unit this variant configures; the unit determines the owning location |
| `--coworker-id` | long | ID of the optional customer this variant is associated with |
| `--name` | string | Required, non-empty display name for this alternate floor plan unit configuration |
| `--size` | decimal | Optional floor area in square metres for this configuration |
| `--capacity` | decimal | Optional number of seats this configuration can accommodate |
| `--price` | decimal | Optional target price in the owning location's currency, used for occupancy reporting rather than billing |
| `--occupancy-percentage` | decimal | Percentage of the floor plan unit's total possible use reported when this package is contracted; normally divide use evenly across packages according to the number of weekdays each is available |
| `--notes` | string | Optional internal notes about this configuration, limited to 255 characters |
| `--available-monday` | bool | Whether this configuration is marked available on Monday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-tuesday` | bool | Whether this configuration is marked available on Tuesday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-wednesday` | bool | Whether this configuration is marked available on Wednesday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-thursday` | bool | Whether this configuration is marked available on Thursday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-friday` | bool | Whether this configuration is marked available on Friday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-saturday` | bool | Whether this configuration is marked available on Saturday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-sunday` | bool | Whether this configuration is marked available on Sunday; scheduling conflict checks treat matching enabled weekday flags as overlapping |
| `--available-from-time` | DateTime | Optional inclusive UTC start of this configuration's availability window; it must precede AvailableToTime when both are set |
| `--available-to-time` | DateTime | Optional inclusive UTC end of this configuration's availability window; null means no end, and it must follow AvailableFromTime when both are set |

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
