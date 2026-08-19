# ProposalSchedules

<!-- BEGIN:GENERATED entity=ProposalSchedules -->

A **ProposalSchedule** defines the overall timeline and milestones for a proposal, including validity period and follow-up dates.

ProposalSchedules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposalschedules list --agent` | List all proposalschedules |
| `nexudus proposalschedules list --id <id> --agent` | Filter by single ID |
| `nexudus proposalschedules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposalschedules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposalschedules list --proposal-tariff-name <value> --proposal-coworker-full-name <value> --agent` | Filter proposalschedules by properties |
| `nexudus proposalschedules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposalschedules list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus proposalschedules get <id> --agent` | Get single proposalschedule |
| `nexudus proposalschedules create --proposal-id <value> --apply-on <value> --agent` | Create proposalschedule |
| `nexudus proposalschedules update <id> --name "New Name" --agent` | Update proposalschedule |
| `nexudus proposalschedules delete <id> --yes --agent` | Delete proposalschedule (no prompt) |

#### ProposalSchedule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long | ID of the proposal linked to this record |
| `--proposal-quantity` | int | Proposal quantity |
| `--from-proposal-quantity` | range | |
| `--to-proposal-quantity` | range | |
| `--proposal-tariff-name` | string | Proposal tariff name |
| `--proposal-coworker-id` | int | Proposal coworker ID |
| `--from-proposal-coworker-id` | range | |
| `--to-proposal-coworker-id` | range | |
| `--proposal-coworker-full-name` | string | Proposal coworker full name |
| `--proposal-coworker-billing-name` | string | Proposal coworker billing name |
| `--notes` | string | Optional notes or comments about this proposal schedule |
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

#### ProposalSchedule sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ProposalSchedule create options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long, required | ID of the proposal linked to this record |
| `--notes` | string | Optional notes or comments about this proposal schedule |
| `--price` | decimal | Scheduled price |
| `--apply-on` | DateTime, required | Date to apply |

#### ProposalSchedule update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long | ID of the proposal linked to this record |
| `--notes` | string | Optional notes or comments about this proposal schedule |
| `--price` | decimal | Scheduled price |
| `--apply-on` | DateTime | Date to apply |

#### ProposalSchedule PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--proposal-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--proposal-coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus proposalschedules update <id> --proposal-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### ProposalSchedule (key fields)

`Id`, `ProposalTariffName`, `ProposalCoworkerFullName`, `Price`, `ApplyOn`

<!-- END:GENERATED entity=ProposalSchedules -->
