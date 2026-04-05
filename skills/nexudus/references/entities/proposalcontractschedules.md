# ProposalContractSchedules

<!-- BEGIN:GENERATED entity=ProposalContractSchedules -->

ProposalContractSchedules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposalcontractschedules list --agent` | List all proposalcontractschedules |
| `nexudus proposalcontractschedules list --id <id> --agent` | Filter by single ID |
| `nexudus proposalcontractschedules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposalcontractschedules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposalcontractschedules list --price <value> --apply-on <value> --agent` | Filter proposalcontractschedules by properties |
| `nexudus proposalcontractschedules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposalcontractschedules get <id> --agent` | Get single proposalcontractschedule |
| `nexudus proposalcontractschedules create --proposal-contract-id <value> --apply-on <value> --agent` | Create proposalcontractschedule |
| `nexudus proposalcontractschedules update <id> --name "New Name" --agent` | Update proposalcontractschedule |
| `nexudus proposalcontractschedules delete <id> --yes --agent` | Delete proposalcontractschedule (no prompt) |

#### ProposalContractSchedule list filter options

`--proposal-contract-id`, `--notes`, `--price`, `--from-price` (range), `--to-price` (range), `--apply-on`, `--from-apply-on` (range), `--to-apply-on` (range), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ProposalContractSchedule create options

`--proposal-contract-id` (required), `--notes`, `--price`, `--apply-on` (required)

#### ProposalContractSchedule update options

`--proposal-contract-id`, `--notes`, `--price`, `--apply-on`

### ProposalContractSchedule (key fields)

`Id`, `ProposalContractTariffName`, `ProposalContractProposalCoworkerFullName`, `Price`, `ApplyOn`

<!-- END:GENERATED entity=ProposalContractSchedules -->
