# ProposalSchedules

<!-- BEGIN:GENERATED entity=ProposalSchedules -->

ProposalSchedules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposalschedules list --agent` | List all proposalschedules |
| `nexudus proposalschedules list --id <id> --agent` | Filter by single ID |
| `nexudus proposalschedules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposalschedules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposalschedules list --price <value> --apply-on <value> --agent` | Filter proposalschedules by properties |
| `nexudus proposalschedules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposalschedules get <id> --agent` | Get single proposalschedule |
| `nexudus proposalschedules create --proposal-id <value> --apply-on <value> --agent` | Create proposalschedule |
| `nexudus proposalschedules update <id> --name "New Name" --agent` | Update proposalschedule |
| `nexudus proposalschedules delete <id> --yes --agent` | Delete proposalschedule (no prompt) |

#### ProposalSchedule list filter options

`--proposal-id`, `--notes`, `--price`, `--apply-on`

#### ProposalSchedule create options

`--proposal-id` (required), `--notes`, `--price`, `--apply-on` (required)

#### ProposalSchedule update options

`--proposal-id`, `--notes`, `--price`, `--apply-on`

### ProposalSchedule (key fields)

`Id`, `ProposalTariffName`, `ProposalCoworkerFullName`, `Price`, `ApplyOn`

<!-- END:GENERATED entity=ProposalSchedules -->
