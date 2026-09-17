# ProposalContractSchedules

<!-- BEGIN:GENERATED entity=ProposalContractSchedules -->

A ProposalContractSchedule is a future price change on one quoted contract inside a proposal: a new unit price and the date it takes effect. Each one becomes a scheduled price change on the customer's real contract when the proposal is accepted. This is where scheduled price changes are managed once a proposal has been created.

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
| `--proposal-contract-id` | long | ID of the quoted contract this price change belongs to; required, and the issuing location of that contract's proposal owns this record. |
| `--proposal-contract-quantity` | int | Display value for ProposalContract.Quantity. |
| `--from-proposal-contract-quantity` | range | |
| `--to-proposal-contract-quantity` | range | |
| `--proposal-contract-tariff-name` | string | Display value for ProposalContract.Tariff.Name. |
| `--proposal-contract-coworker-id` | int | Display value for ProposalContract.Proposal.Coworker.Id. |
| `--from-proposal-contract-coworker-id` | range | |
| `--to-proposal-contract-coworker-id` | range | |
| `--proposal-contract-coworker-full-name` | string | Display value for ProposalContract.Proposal.Coworker.FullName. |
| `--proposal-contract-coworker-billing-name` | string | Display value for ProposalContract.Proposal.Coworker.BillingName. |
| `--notes` | string | Free-text note explaining the price change; it is carried onto the customer contract's schedule on acceptance. |
| `--price` | decimal | New per-unit price that takes effect on ApplyOn, in the issuing location's currency. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--apply-on` | DateTime | Date the new price takes effect; required, and each price change on the same quoted contract needs its own date. |
| `--from-apply-on` | range | |
| `--to-apply-on` | range | |
| `--applied` | bool | Read-only flag recording whether this price change has already been applied; the billing run sets it and it is not changed through proposal administration. |
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
| `--proposal-contract-id` | long, required | ID of the quoted contract this price change belongs to; required, and the issuing location of that contract's proposal owns this record. |
| `--notes` | string | Free-text note explaining the price change; it is carried onto the customer contract's schedule on acceptance. |
| `--price` | decimal | New per-unit price that takes effect on ApplyOn, in the issuing location's currency. |
| `--apply-on` | DateTime, required | Date the new price takes effect; required, and each price change on the same quoted contract needs its own date. |

#### ProposalContractSchedule update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-contract-id` | long | ID of the quoted contract this price change belongs to; required, and the issuing location of that contract's proposal owns this record. |
| `--notes` | string | Free-text note explaining the price change; it is carried onto the customer contract's schedule on acceptance. |
| `--price` | decimal | New per-unit price that takes effect on ApplyOn, in the issuing location's currency. |
| `--apply-on` | DateTime | Date the new price takes effect; required, and each price change on the same quoted contract needs its own date. |

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
