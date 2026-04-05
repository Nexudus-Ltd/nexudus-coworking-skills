# ContractPausedPeriods

<!-- BEGIN:GENERATED entity=ContractPausedPeriods -->

ContractPausedPeriods support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractpausedperiods list --agent` | List all contractpausedperiods |
| `nexudus contractpausedperiods list --id <id> --agent` | Filter by single ID |
| `nexudus contractpausedperiods list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractpausedperiods list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractpausedperiods list --pause-from <value> --pause-until <value> --agent` | Filter contractpausedperiods by properties |
| `nexudus contractpausedperiods list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractpausedperiods get <id> --agent` | Get single contractpausedperiod |
| `nexudus contractpausedperiods create --coworker-contract-id <value> --pause-from <value> --pause-until <value> --agent` | Create contractpausedperiod |
| `nexudus contractpausedperiods update <id> --name "New Name" --agent` | Update contractpausedperiod |
| `nexudus contractpausedperiods delete <id> --yes --agent` | Delete contractpausedperiod (no prompt) |

#### ContractPausedPeriod list filter options

`--coworker-contract-id`, `--notes`, `--pause-from`, `--from-pause-from` (range), `--to-pause-from` (range), `--pause-until`, `--from-pause-until` (range), `--to-pause-until` (range), `--pause-from-local`, `--from-pause-from-local` (range), `--to-pause-from-local` (range), `--pause-until-local`, `--from-pause-until-local` (range), `--to-pause-until-local` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ContractPausedPeriod create options

`--coworker-contract-id` (required), `--notes`, `--pause-from` (required), `--pause-until` (required), `--pause-from-local`, `--pause-until-local`

#### ContractPausedPeriod update options

`--coworker-contract-id`, `--notes`, `--pause-from`, `--pause-until`, `--pause-from-local`, `--pause-until-local`

### ContractPausedPeriod (key fields)

`Id`, `CoworkerContractCoworkerFullName`, `PauseFrom`, `PauseUntil`

<!-- END:GENERATED entity=ContractPausedPeriods -->
