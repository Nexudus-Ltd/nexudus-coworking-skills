# ProposalContracts

<!-- BEGIN:GENERATED entity=ProposalContracts -->

A **ProposalContract** links a contract configuration to a proposal, defining the pricing plan and terms that will be applied if the proposal is accepted by the customer.

ProposalContracts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposalcontracts list --agent` | List all proposalcontracts |
| `nexudus proposalcontracts list --id <id> --agent` | Filter by single ID |
| `nexudus proposalcontracts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposalcontracts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposalcontracts list --proposal-coworker-full-name <value> --tariff-name <value> --agent` | Filter proposalcontracts by properties |
| `nexudus proposalcontracts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposalcontracts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus proposalcontracts get <id> --agent` | Get single proposalcontract |
| `nexudus proposalcontracts create --proposal-id <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create proposalcontract |
| `nexudus proposalcontracts update <id> --name "New Name" --agent` | Update proposalcontract |
| `nexudus proposalcontracts delete <id> --yes --agent` | Delete proposalcontract (no prompt) |

#### ProposalContract list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long | ID of the proposal linked to this record |
| `--proposal-coworker-id` | int | Proposal coworker ID |
| `--from-proposal-coworker-id` | range | |
| `--to-proposal-coworker-id` | range | |
| `--proposal-coworker-email` | string | Proposal coworker email |
| `--proposal-coworker-full-name` | string | Proposal coworker full name |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--tariff-name` | string | Tariff name |
| `--tariff-invoice-every` | int | Tariff invoice frequency |
| `--from-tariff-invoice-every` | range | |
| `--to-tariff-invoice-every` | range | |
| `--tariff-invoice-every-weeks` | int | Tariff invoice frequency in weeks |
| `--from-tariff-invoice-every-weeks` | range | |
| `--to-tariff-invoice-every-weeks` | range | |
| `--tariff-price` | decimal | Tariff price |
| `--from-tariff-price` | range | |
| `--to-tariff-price` | range | |
| `--tariff-business-currency-code` | string | Tariff business currency code |
| `--price` | decimal | Price override |
| `--from-price` | range | |
| `--to-price` | range | |
| `--start-date` | DateTime | Contract start date |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--cancellation-limit-days` | int | Cancellation limit in days |
| `--from-cancellation-limit-days` | range | |
| `--to-cancellation-limit-days` | range | |
| `--contract-term` | DateTime | Contract term end date |
| `--from-contract-term` | range | |
| `--to-contract-term` | range | |
| `--cancellation-date` | DateTime | Cancellation date |
| `--from-cancellation-date` | range | |
| `--to-cancellation-date` | range | |
| `--billing-day` | int | Billing day of month |
| `--from-billing-day` | range | |
| `--to-billing-day` | range | |
| `--quantity` | int | Number of units |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--discount-code-id` | long | ID of the discount code linked to this record |
| `--floor-plan-desk-ids` | string | Floor plan desk IDs |
| `--floor-plan-desk-names` | string | Floor plan desk names |
| `--floor-plan-desk-variant-ids` | string | Floor plan desk variant IDs |
| `--floor-plan-desk-variant-names` | string | Floor plan desk variant names |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ProposalContract sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ProposalContract create options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long, required | ID of the proposal linked to this record |
| `--tariff-id` | long, required | ID of the tariff linked to this record |
| `--desks` | list, repeat flag | List of desks linked to this record |
| `--added-desks` | list, repeat flag | The added desks value for this proposal contract |
| `--removed-desks` | list, repeat flag | The removed desks value for this proposal contract |
| `--variants` | list, repeat flag | List of variants linked to this record |
| `--added-variants` | list, repeat flag | The added variants value for this proposal contract |
| `--removed-variants` | list, repeat flag | The removed variants value for this proposal contract |
| `--price` | decimal | Price override |
| `--start-date` | DateTime | Contract start date |
| `--cancellation-limit-days` | int | Cancellation limit in days |
| `--contract-term` | DateTime | Contract term end date |
| `--cancellation-date` | DateTime | Cancellation date |
| `--billing-day` | int, required | Billing day of month |
| `--quantity` | int, required | Number of units |
| `--discount-code-id` | long | ID of the discount code linked to this record |

#### ProposalContract update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long | ID of the proposal linked to this record |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--desks` | list, repeat flag | List of desks linked to this record |
| `--added-desks` | list, repeat flag | The added desks value for this proposal contract |
| `--removed-desks` | list, repeat flag | The removed desks value for this proposal contract |
| `--variants` | list, repeat flag | List of variants linked to this record |
| `--added-variants` | list, repeat flag | The added variants value for this proposal contract |
| `--removed-variants` | list, repeat flag | The removed variants value for this proposal contract |
| `--price` | decimal | Price override |
| `--start-date` | DateTime | Contract start date |
| `--cancellation-limit-days` | int | Cancellation limit in days |
| `--contract-term` | DateTime | Contract term end date |
| `--cancellation-date` | DateTime | Cancellation date |
| `--billing-day` | int | Billing day of month |
| `--quantity` | int | Number of units |
| `--discount-code-id` | long | ID of the discount code linked to this record |

#### ProposalContract PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--proposal-coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--proposal-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |

Example:

`nexudus proposalcontracts update <id> --proposal-coworker-email "«PII:EMAIL:a3f2b1c9»" --agent`

### ProposalContract (key fields)

`Id`, `ProposalCoworkerFullName`, `TariffName`, `Price`, `StartDate`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`

<!-- END:GENERATED entity=ProposalContracts -->
