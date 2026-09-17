# ProposalContracts

<!-- BEGIN:GENERATED entity=ProposalContracts -->

A ProposalContract is one quoted contract inside a proposal. It carries the same plan, unit, price, date, and quantity settings as a customer contract and becomes a real contract for the customer when the proposal is accepted. One is created automatically with the proposal from the proposal's own contract fields; add more to quote several contracts in a single offer. Changes to the plan, units, price, or dates of an existing proposal belong here rather than on the proposal itself.

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
| `--proposal-id` | long | ID of the proposal this quoted contract belongs to; required, and the proposal's issuing location owns this record. |
| `--proposal-coworker-id` | int | Display value for Proposal.Coworker.Id. |
| `--from-proposal-coworker-id` | range | |
| `--to-proposal-coworker-id` | range | |
| `--proposal-coworker-email` | string | Display value for Proposal.Coworker.Email. |
| `--proposal-coworker-full-name` | string | Display value for Proposal.Coworker.FullName. |
| `--tariff-id` | long | ID of the plan quoted by this contract; required, and its billing interval, price, and policies govern the contract the customer receives on acceptance. |
| `--tariff-name` | string | Display value for Tariff.Name. |
| `--tariff-invoice-every` | int | Display value for Tariff.InvoiceEvery. |
| `--from-tariff-invoice-every` | range | |
| `--to-tariff-invoice-every` | range | |
| `--tariff-invoice-every-weeks` | int | Display value for Tariff.InvoiceEveryWeeks. |
| `--from-tariff-invoice-every-weeks` | range | |
| `--to-tariff-invoice-every-weeks` | range | |
| `--tariff-price` | decimal | Display value for Tariff.Price. |
| `--from-tariff-price` | range | |
| `--to-tariff-price` | range | |
| `--tariff-business-currency-code` | string | Display value for Tariff.Business.Currency.Code. |
| `--price` | decimal | Optional per-unit price override for this quoted contract, in the issuing location's currency; when empty the plan's own price is used before quantity is applied. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--start-date` | DateTime | Date the contract starts once the proposal is accepted; when empty, acceptance starts it the day after the proposal is accepted. |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice, in days before the next billing day; when empty the plan's own notice period applies. |
| `--from-cancellation-limit-days` | range | |
| `--to-cancellation-limit-days` | range | |
| `--contract-term` | DateTime | Optional end date of the minimum contract term, carried onto the customer contract on acceptance; when empty the contract derives its own term from the plan's default term and start date. |
| `--from-contract-term` | range | |
| `--to-contract-term` | range | |
| `--cancellation-date` | DateTime | Optional date on which the contract ends; leave it empty for an open-ended contract. |
| `--from-cancellation-date` | range | |
| `--to-cancellation-date` | range | |
| `--billing-day` | int | Day of the month, from 1 to 28, on which the contract is invoiced after acceptance. |
| `--from-billing-day` | range | |
| `--to-billing-day` | range | |
| `--quantity` | int | Number of plan units on this quoted contract, at least 1; it multiplies the unit price. |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--discount-code-id` | long | Optional ID of a discount code carried onto the customer contract when the proposal is accepted. |
| `--floor-plan-desk-ids` | string | Read-only denormalized IDs of the assigned floor-plan units; change Desks rather than this projection. |
| `--floor-plan-desk-names` | string | Read-only denormalized names of the assigned floor-plan units; change Desks rather than this projection. |
| `--floor-plan-desk-variant-ids` | string | Read-only denormalized IDs of the assigned floor-plan unit packages; change Variants rather than this projection. |
| `--floor-plan-desk-variant-names` | string | Read-only denormalized names of the assigned floor-plan unit packages; change Variants rather than this projection. |
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
| `--proposal-id` | long, required | ID of the proposal this quoted contract belongs to; required, and the proposal's issuing location owns this record. |
| `--tariff-id` | long, required | ID of the plan quoted by this contract; required, and its billing interval, price, and policies govern the contract the customer receives on acceptance. |
| `--desks` | list, repeat flag | List of IDs of the floor-plan units assigned to this quoted contract; each unit must belong to a location the user can access, an empty list means no unit is attached, and these are the units the customer receives on acceptance. |
| `--added-desks` | list, repeat flag | IDs added to the Desks relationship. |
| `--removed-desks` | list, repeat flag | IDs removed from the Desks relationship. |
| `--variants` | list, repeat flag | List of IDs of the floor-plan unit packages assigned to this quoted contract; each package must belong to one of the units listed in Desks and to a location the user can access. |
| `--added-variants` | list, repeat flag | IDs added to the Variants relationship. |
| `--removed-variants` | list, repeat flag | IDs removed from the Variants relationship. |
| `--price` | decimal | Optional per-unit price override for this quoted contract, in the issuing location's currency; when empty the plan's own price is used before quantity is applied. |
| `--start-date` | DateTime | Date the contract starts once the proposal is accepted; when empty, acceptance starts it the day after the proposal is accepted. |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice, in days before the next billing day; when empty the plan's own notice period applies. |
| `--contract-term` | DateTime | Optional end date of the minimum contract term, carried onto the customer contract on acceptance; when empty the contract derives its own term from the plan's default term and start date. |
| `--cancellation-date` | DateTime | Optional date on which the contract ends; leave it empty for an open-ended contract. |
| `--billing-day` | int, required | Day of the month, from 1 to 28, on which the contract is invoiced after acceptance. |
| `--quantity` | int, required | Number of plan units on this quoted contract, at least 1; it multiplies the unit price. |
| `--discount-code-id` | long | Optional ID of a discount code carried onto the customer contract when the proposal is accepted. |

#### ProposalContract update options

| Option | Type | Description |
| --- | --- | --- |
| `--proposal-id` | long | ID of the proposal this quoted contract belongs to; required, and the proposal's issuing location owns this record. |
| `--tariff-id` | long | ID of the plan quoted by this contract; required, and its billing interval, price, and policies govern the contract the customer receives on acceptance. |
| `--desks` | list, repeat flag | List of IDs of the floor-plan units assigned to this quoted contract; each unit must belong to a location the user can access, an empty list means no unit is attached, and these are the units the customer receives on acceptance. |
| `--added-desks` | list, repeat flag | IDs added to the Desks relationship. |
| `--removed-desks` | list, repeat flag | IDs removed from the Desks relationship. |
| `--variants` | list, repeat flag | List of IDs of the floor-plan unit packages assigned to this quoted contract; each package must belong to one of the units listed in Desks and to a location the user can access. |
| `--added-variants` | list, repeat flag | IDs added to the Variants relationship. |
| `--removed-variants` | list, repeat flag | IDs removed from the Variants relationship. |
| `--price` | decimal | Optional per-unit price override for this quoted contract, in the issuing location's currency; when empty the plan's own price is used before quantity is applied. |
| `--start-date` | DateTime | Date the contract starts once the proposal is accepted; when empty, acceptance starts it the day after the proposal is accepted. |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice, in days before the next billing day; when empty the plan's own notice period applies. |
| `--contract-term` | DateTime | Optional end date of the minimum contract term, carried onto the customer contract on acceptance; when empty the contract derives its own term from the plan's default term and start date. |
| `--cancellation-date` | DateTime | Optional date on which the contract ends; leave it empty for an open-ended contract. |
| `--billing-day` | int | Day of the month, from 1 to 28, on which the contract is invoiced after acceptance. |
| `--quantity` | int | Number of plan units on this quoted contract, at least 1; it multiplies the unit price. |
| `--discount-code-id` | long | Optional ID of a discount code carried onto the customer contract when the proposal is accepted. |

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
