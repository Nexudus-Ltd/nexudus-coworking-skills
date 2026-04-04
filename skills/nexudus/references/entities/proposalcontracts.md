# ProposalContracts

<!-- BEGIN:GENERATED entity=ProposalContracts -->

ProposalContracts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposalcontracts list --agent` | List all proposalcontracts |
| `nexudus proposalcontracts list --id <id> --agent` | Filter by single ID |
| `nexudus proposalcontracts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposalcontracts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposalcontracts list --price <value> --start-date <value> --agent` | Filter proposalcontracts by properties |
| `nexudus proposalcontracts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposalcontracts get <id> --agent` | Get single proposalcontract |
| `nexudus proposalcontracts create --proposal-id <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create proposalcontract |
| `nexudus proposalcontracts update <id> --name "New Name" --agent` | Update proposalcontract |
| `nexudus proposalcontracts delete <id> --yes --agent` | Delete proposalcontract (no prompt) |

#### ProposalContract list filter options

`--proposal-id`, `--tariff-id`, `--price`, `--start-date`, `--cancellation-limit-days`, `--contract-term`, `--cancellation-date`, `--billing-day`, `--quantity`, `--discount-code-id`

#### ProposalContract create options

`--proposal-id` (required), `--tariff-id` (required), `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--variants` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--price`, `--start-date`, `--cancellation-limit-days`, `--contract-term`, `--cancellation-date`, `--billing-day` (required), `--quantity` (required), `--discount-code-id`, `--schedules` (list, repeat flag), `--added-schedules` (list, repeat flag), `--removed-schedules` (list, repeat flag)

#### ProposalContract update options

`--proposal-id`, `--tariff-id`, `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--variants` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--price`, `--start-date`, `--cancellation-limit-days`, `--contract-term`, `--cancellation-date`, `--billing-day`, `--quantity`, `--discount-code-id`, `--schedules` (list, repeat flag), `--added-schedules` (list, repeat flag), `--removed-schedules` (list, repeat flag)

### ProposalContract (key fields)

`Id`, `ProposalCoworkerFullName`, `TariffName`, `Price`, `StartDate`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`, `Schedules`, `AddedSchedules`, `RemovedSchedules`

<!-- END:GENERATED entity=ProposalContracts -->
