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

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-contract-id` | long |  |
| `--notes` | string | Notes |
| `--price` | decimal | Scheduled price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--apply-on` | DateTime | Date to apply |
| `--from-apply-on` | range | |
| `--to-apply-on` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProposalContractSchedule create options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-contract-id` | long, required |  |
| `--notes` | string | Notes |
| `--price` | decimal | Scheduled price |
| `--apply-on` | DateTime, required | Date to apply |

#### ProposalContractSchedule update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-contract-id` | long |  |
| `--notes` | string | Notes |
| `--price` | decimal | Scheduled price |
| `--apply-on` | DateTime | Date to apply |

#### ProposalContractSchedule PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--proposal-contract-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--proposal-contract-coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus proposalcontractschedules update <id> --proposal-contract-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### ProposalContractSchedule (key fields)

`Id`, `ProposalContractTariffName`, `ProposalContractProposalCoworkerFullName`, `Price`, `ApplyOn`

<!-- END:GENERATED entity=ProposalContractSchedules -->
