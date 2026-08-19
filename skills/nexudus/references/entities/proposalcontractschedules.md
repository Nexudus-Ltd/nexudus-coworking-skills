# ProposalContractSchedules

<!-- BEGIN:GENERATED entity=ProposalContractSchedules -->

A **ProposalContractSchedule** defines the billing schedule for a contract within a proposal, specifying payment frequency, amounts, and timing.

ProposalContractSchedules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposalcontractschedules list --agent` | List all proposalcontractschedules |
| `nexudus proposalcontractschedules list --id <id> --agent` | Filter by single ID |
| `nexudus proposalcontractschedules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposalcontractschedules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposalcontractschedules list --proposal-contract-tariff-name <value> --proposal-contract-coworker-full-name <value> --agent` | Filter proposalcontractschedules by properties |
| `nexudus proposalcontractschedules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposalcontractschedules list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus proposalcontractschedules get <id> --agent` | Get single proposalcontractschedule |
| `nexudus proposalcontractschedules create --proposal-contract-id <value> --apply-on <value> --agent` | Create proposalcontractschedule |
| `nexudus proposalcontractschedules update <id> --name "New Name" --agent` | Update proposalcontractschedule |
| `nexudus proposalcontractschedules delete <id> --yes --agent` | Delete proposalcontractschedule (no prompt) |

#### ProposalContractSchedule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-contract-id` | long | ID of the proposal contract linked to this record |
| `--proposal-contract-quantity` | int | Proposal contract quantity |
| `--from-proposal-contract-quantity` | range | |
| `--to-proposal-contract-quantity` | range | |
| `--proposal-contract-tariff-name` | string | Proposal contract tariff name |
| `--proposal-contract-coworker-id` | int | Proposal contract coworker ID |
| `--from-proposal-contract-coworker-id` | range | |
| `--to-proposal-contract-coworker-id` | range | |
| `--proposal-contract-coworker-full-name` | string | Proposal contract coworker full name |
| `--proposal-contract-coworker-billing-name` | string | Proposal contract coworker billing name |
| `--notes` | string | Optional notes or comments about this proposal contract schedule |
| `--price` | decimal | Scheduled price |
| `--from-price` | range | |
| `--to-price` | range | |
| `--apply-on` | DateTime | Date to apply |
| `--from-apply-on` | range | |
| `--to-apply-on` | range | |
| `--applied` | bool | Whether the schedule has been applied |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProposalContractSchedule sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ProposalContractSchedule create options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-contract-id` | long, required | ID of the proposal contract linked to this record |
| `--notes` | string | Optional notes or comments about this proposal contract schedule |
| `--price` | decimal | Scheduled price |
| `--apply-on` | DateTime, required | Date to apply |

#### ProposalContractSchedule update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-contract-id` | long | ID of the proposal contract linked to this record |
| `--notes` | string | Optional notes or comments about this proposal contract schedule |
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
