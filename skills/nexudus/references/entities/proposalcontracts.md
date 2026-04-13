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

`--proposal-id` (long), `--tariff-id` (long), `--price` (decimal), `--from-price` (range), `--to-price` (range), `--start-date` (DateTime), `--from-start-date` (range), `--to-start-date` (range), `--cancellation-limit-days` (int), `--from-cancellation-limit-days` (range), `--to-cancellation-limit-days` (range), `--contract-term` (DateTime), `--from-contract-term` (range), `--to-contract-term` (range), `--cancellation-date` (DateTime), `--from-cancellation-date` (range), `--to-cancellation-date` (range), `--billing-day` (int), `--from-billing-day` (range), `--to-billing-day` (range), `--quantity` (int), `--from-quantity` (range), `--to-quantity` (range), `--discount-code-id` (long), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ProposalContract create options

`--proposal-id` (long, required), `--tariff-id` (long, required), `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--variants` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--price` (decimal), `--start-date` (DateTime), `--cancellation-limit-days` (int), `--contract-term` (DateTime), `--cancellation-date` (DateTime), `--billing-day` (int, required), `--quantity` (int, required), `--discount-code-id` (long)

#### ProposalContract update options

`--proposal-id` (long), `--tariff-id` (long), `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--variants` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--price` (decimal), `--start-date` (DateTime), `--cancellation-limit-days` (int), `--contract-term` (DateTime), `--cancellation-date` (DateTime), `--billing-day` (int), `--quantity` (int), `--discount-code-id` (long)

### ProposalContract (key fields)

`Id`, `ProposalCoworkerFullName`, `TariffName`, `Price`, `StartDate`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`

<!-- END:GENERATED entity=ProposalContracts -->
