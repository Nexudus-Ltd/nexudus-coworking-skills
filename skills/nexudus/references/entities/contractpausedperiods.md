# ContractPausedPeriods

<!-- BEGIN:GENERATED entity=ContractPausedPeriods -->

A **ContractPausedPeriod** represents a freeze period applied to a customer's plan contract (`CoworkerContract`). Plan freezing lets admins — and optionally customers — suspend a contract for one or more billing cycles without cancelling it.

Freeze dates are always aligned to billing cycle boundaries: `PauseFrom` is always the first day of the customer's next billing cycle, and `PauseUntil` is always the first day of the billing cycle when the plan is due to restart.

While a contract is frozen:
- No charges are generated for the contract for the duration of the freeze.
- The customer's status reverts to **Contact** if they have no other active contract.
- No member rates or benefits from the frozen contract apply during the freeze.
- Invoices are still generated on the usual billing day for any purchases (bookings, products) linked to the contract.

Admins can freeze contracts from the customer's account, via teams, or in bulk from Finance > Contracts. Whether customers can freeze their own plans from the Members Portal is controlled by the `AllowContractFreezing` setting on the plan (`Tariff`).

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

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the customer contract being frozen |
| `--notes` | string | Optional notes or reason for this freeze period |
| `--pause-from` | DateTime | UTC date when the freeze starts. Always falls on the first day of a billing cycle |
| `--from-pause-from` | range | |
| `--to-pause-from` | range | |
| `--pause-until` | DateTime | UTC date when the freeze ends. Always falls on the first day of the billing cycle when the plan is due to restart |
| `--from-pause-until` | range | |
| `--to-pause-until` | range | |
| `--pause-from-local` | DateTime | Location-timezone equivalent of PauseFrom |
| `--from-pause-from-local` | range | |
| `--to-pause-from-local` | range | |
| `--pause-until-local` | DateTime | Location-timezone equivalent of PauseUntil |
| `--from-pause-until-local` | range | |
| `--to-pause-until-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractPausedPeriod create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long, required | ID of the customer contract being frozen |
| `--notes` | string | Optional notes or reason for this freeze period |
| `--pause-from` | DateTime, required | UTC date when the freeze starts. Always falls on the first day of a billing cycle |
| `--pause-until` | DateTime, required | UTC date when the freeze ends. Always falls on the first day of the billing cycle when the plan is due to restart |
| `--pause-from-local` | DateTime | Location-timezone equivalent of PauseFrom |
| `--pause-until-local` | DateTime | Location-timezone equivalent of PauseUntil |

#### ContractPausedPeriod update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the customer contract being frozen |
| `--notes` | string | Optional notes or reason for this freeze period |
| `--pause-from` | DateTime | UTC date when the freeze starts. Always falls on the first day of a billing cycle |
| `--pause-until` | DateTime | UTC date when the freeze ends. Always falls on the first day of the billing cycle when the plan is due to restart |
| `--pause-from-local` | DateTime | Location-timezone equivalent of PauseFrom |
| `--pause-until-local` | DateTime | Location-timezone equivalent of PauseUntil |

### ContractPausedPeriod (key fields)

`Id`, `CoworkerContractTariffName`, `CoworkerContractCoworkerFullName`, `PauseFrom`, `PauseUntil`

<!-- END:GENERATED entity=ContractPausedPeriods -->
