# ContractSchedules

<!-- BEGIN:GENERATED entity=ContractSchedules -->

A **ContractSchedule** defines a future price change for a plan contract (`CoworkerContract`). On the date specified by `ApplyOn`, the system automatically updates the contract's price to the value in `Price`.

Schedules allow operators to pre-configure stepped pricing — for example, an introductory rate for the first few months that transitions to a full rate on a known date — without any manual intervention at the time of the change.

Once a schedule has been processed, `Applied` is set to `true` and the record becomes read-only.

ContractSchedules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractschedules list --agent` | List all contractschedules |
| `nexudus contractschedules list --id <id> --agent` | Filter by single ID |
| `nexudus contractschedules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractschedules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractschedules list --price <value> --apply-on <value> --agent` | Filter contractschedules by properties |
| `nexudus contractschedules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractschedules get <id> --agent` | Get single contractschedule |
| `nexudus contractschedules create --coworker-contract-id <value> --apply-on <value> --agent` | Create contractschedule |
| `nexudus contractschedules update <id> --name "New Name" --agent` | Update contractschedule |
| `nexudus contractschedules delete <id> --yes --agent` | Delete contractschedule (no prompt) |

#### ContractSchedule list filter options

`--coworker-contract-id`, `--notes`, `--price`, `--apply-on`, `--apply-on-local`

#### ContractSchedule create options

`--coworker-contract-id` (required), `--notes`, `--price`, `--apply-on` (required), `--apply-on-local`

#### ContractSchedule update options

`--coworker-contract-id`, `--notes`, `--price`, `--apply-on`, `--apply-on-local`

### ContractSchedule (key fields)

`Id`, `CoworkerContractCoworkerFullName`, `Price`, `ApplyOn`, `Applied`

<!-- END:GENERATED entity=ContractSchedules -->
