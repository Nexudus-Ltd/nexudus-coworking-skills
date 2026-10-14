# IndexationRules

<!-- BEGIN:GENERATED entity=IndexationRules -->

An IndexationRule steps the unit price of the contracts it is attached to by a percentage or a fixed amount every FrequencyMonths, for as long as each contract is active. Steps are anchored on the contract anniversary or on a fixed day of the year, compound on the then-current price (including any manual price schedule applied before them) and apply from the first billing period starting on or after the step date. The first step copies the plan price into the contract's own unit price when the contract had none, and from then on the contract no longer follows changes to the plan price. A rule is owned by a location for audit only and can be attached to contracts at any location the user can see, through the contract's indexationRuleId, a plan's defaultIndexationRuleId (new contracts only) or a proposal contract. Switch a rule off instead of deleting it when contracts use it; delete is refused while any contract or proposal contract references the rule.

IndexationRules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus indexationrules list --agent` | List all indexationrules |
| `nexudus indexationrules list --id <id> --agent` | Filter by single ID |
| `nexudus indexationrules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus indexationrules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus indexationrules list --business-id <value> --business-name <value> --agent` | Filter indexationrules by properties |
| `nexudus indexationrules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus indexationrules list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus indexationrules get <id> --agent` | Get single indexationrule |
| `nexudus indexationrules create --business-id <value> --name <value> --adjustment-type <value> --amount <value> --anchor-type <value> --frequency-months <value> --minimum-months-before-first <value> --notice-days <value> --agent` | Create indexationrule |
| `nexudus indexationrules update <id> --name "New Name" --agent` | Update indexationrule |
| `nexudus indexationrules delete <id> --yes --agent` | Delete indexationrule (no prompt) |

#### IndexationRule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns the rule. Ownership only matters for audit and permissions. A rule can be attached to contracts at any location the user can see, and list returns rules from every accessible location unless business_id is given. |
| `--business-name` | string | Display value for Business.Name. |
| `--business-currency-code` | string | Display value for Business.Currency.Code. |
| `--name` | string | Short name shown on contracts, proposals and reports, for example Annual 3% review or CPI January. |
| `--description` | string | Internal notes about the rule. Never shown to customers. |
| `--adjustment-type` | enum | Percentage (Amount is a percent, 3.5 means plus 3.5% of the current unit price) or FixedAmount (Amount is added to the unit price, in the currency of each contract it applies to). |
| `--amount` | decimal | Size of each step, as a percent or an amount per unit depending on AdjustmentType. Negative values lower the price. Must not be 0. |
| `--from-amount` | range | |
| `--to-amount` | range | |
| `--rounding-increment` | decimal | Increment the new unit price is rounded to after each step, midpoint away from zero. Empty rounds to 0.01. Allowed values are 0.1, 0.5, 1, 5, 10 and 100. |
| `--from-rounding-increment` | range | |
| `--to-rounding-increment` | range | |
| `--anchor-type` | enum | ContractAnniversary counts steps from each contract start date (the first step is FrequencyMonths after the start). FixedDate puts the first step on the first AnchorMonth and AnchorDay after the contract start, then every FrequencyMonths. |
| `--anchor-month` | int | Month (1 to 12) of the fixed step date. Required when AnchorType is FixedDate, ignored otherwise. |
| `--from-anchor-month` | range | |
| `--to-anchor-month` | range | |
| `--anchor-day` | int | Day of the month (1 to 28) of the fixed step date. Required when AnchorType is FixedDate, ignored otherwise. |
| `--from-anchor-day` | range | |
| `--to-anchor-day` | range | |
| `--frequency-months` | int | Months between steps, 1 to 120. 12 is a yearly review. |
| `--from-frequency-months` | range | |
| `--to-frequency-months` | range | |
| `--minimum-months-before-first` | int | Steps earlier than this many months after the contract start are skipped, for example so a contract signed in November is not reviewed on 1 January two months later. 0 applies the first step on its regular date. |
| `--from-minimum-months-before-first` | range | |
| `--to-minimum-months-before-first` | range | |
| `--apply-to-contract-products` | bool | When true each step also adjusts the unit price of the products on the contract (ContractProduct). Deposits and plan components are never adjusted. |
| `--clause-text` | string | Sentence shown on proposals and documents for contracts using this rule, for example Prices are reviewed annually and increase by 3%. |
| `--notify-customers` | bool | Email the customer NoticeDays before each step, or right after a step when there was no advance notice. False sends no customer emails for this rule. |
| `--notice-days` | int | Days before a step the customer is emailed, 0 to 180. 0 sends the email after the step instead. |
| `--from-notice-days` | range | |
| `--to-notice-days` | range | |
| `--active` | bool | Whether the rule still applies. Switching it off stops future steps on every contract using it; prices already applied and the history stay. |
| `--archived` | bool | Hides the rule from pickers. Contracts already using it keep working while Active is true. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### IndexationRule sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Name` ascending. If no `--order-by` is specified, the API returns results ordered by `Name` (ascending).

#### IndexationRule create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns the rule. Ownership only matters for audit and permissions. A rule can be attached to contracts at any location the user can see, and list returns rules from every accessible location unless business_id is given. |
| `--name` | string, required | Short name shown on contracts, proposals and reports, for example Annual 3% review or CPI January. |
| `--description` | string | Internal notes about the rule. Never shown to customers. |
| `--adjustment-type` | enum, required | Percentage (Amount is a percent, 3.5 means plus 3.5% of the current unit price) or FixedAmount (Amount is added to the unit price, in the currency of each contract it applies to). |
| `--amount` | decimal, required | Size of each step, as a percent or an amount per unit depending on AdjustmentType. Negative values lower the price. Must not be 0. |
| `--rounding-increment` | decimal | Increment the new unit price is rounded to after each step, midpoint away from zero. Empty rounds to 0.01. Allowed values are 0.1, 0.5, 1, 5, 10 and 100. |
| `--anchor-type` | enum, required | ContractAnniversary counts steps from each contract start date (the first step is FrequencyMonths after the start). FixedDate puts the first step on the first AnchorMonth and AnchorDay after the contract start, then every FrequencyMonths. |
| `--anchor-month` | int | Month (1 to 12) of the fixed step date. Required when AnchorType is FixedDate, ignored otherwise. |
| `--anchor-day` | int | Day of the month (1 to 28) of the fixed step date. Required when AnchorType is FixedDate, ignored otherwise. |
| `--frequency-months` | int, required | Months between steps, 1 to 120. 12 is a yearly review. |
| `--minimum-months-before-first` | int, required | Steps earlier than this many months after the contract start are skipped, for example so a contract signed in November is not reviewed on 1 January two months later. 0 applies the first step on its regular date. |
| `--apply-to-contract-products` | bool | When true each step also adjusts the unit price of the products on the contract (ContractProduct). Deposits and plan components are never adjusted. |
| `--clause-text` | string | Sentence shown on proposals and documents for contracts using this rule, for example Prices are reviewed annually and increase by 3%. |
| `--notify-customers` | bool | Email the customer NoticeDays before each step, or right after a step when there was no advance notice. False sends no customer emails for this rule. |
| `--notice-days` | int, required | Days before a step the customer is emailed, 0 to 180. 0 sends the email after the step instead. |
| `--active` | bool | Whether the rule still applies. Switching it off stops future steps on every contract using it; prices already applied and the history stay. |
| `--archived` | bool | Hides the rule from pickers. Contracts already using it keep working while Active is true. |

#### IndexationRule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns the rule. Ownership only matters for audit and permissions. A rule can be attached to contracts at any location the user can see, and list returns rules from every accessible location unless business_id is given. |
| `--name` | string | Short name shown on contracts, proposals and reports, for example Annual 3% review or CPI January. |
| `--description` | string | Internal notes about the rule. Never shown to customers. |
| `--adjustment-type` | enum | Percentage (Amount is a percent, 3.5 means plus 3.5% of the current unit price) or FixedAmount (Amount is added to the unit price, in the currency of each contract it applies to). |
| `--amount` | decimal | Size of each step, as a percent or an amount per unit depending on AdjustmentType. Negative values lower the price. Must not be 0. |
| `--rounding-increment` | decimal | Increment the new unit price is rounded to after each step, midpoint away from zero. Empty rounds to 0.01. Allowed values are 0.1, 0.5, 1, 5, 10 and 100. |
| `--anchor-type` | enum | ContractAnniversary counts steps from each contract start date (the first step is FrequencyMonths after the start). FixedDate puts the first step on the first AnchorMonth and AnchorDay after the contract start, then every FrequencyMonths. |
| `--anchor-month` | int | Month (1 to 12) of the fixed step date. Required when AnchorType is FixedDate, ignored otherwise. |
| `--anchor-day` | int | Day of the month (1 to 28) of the fixed step date. Required when AnchorType is FixedDate, ignored otherwise. |
| `--frequency-months` | int | Months between steps, 1 to 120. 12 is a yearly review. |
| `--minimum-months-before-first` | int | Steps earlier than this many months after the contract start are skipped, for example so a contract signed in November is not reviewed on 1 January two months later. 0 applies the first step on its regular date. |
| `--apply-to-contract-products` | bool | When true each step also adjusts the unit price of the products on the contract (ContractProduct). Deposits and plan components are never adjusted. |
| `--clause-text` | string | Sentence shown on proposals and documents for contracts using this rule, for example Prices are reviewed annually and increase by 3%. |
| `--notify-customers` | bool | Email the customer NoticeDays before each step, or right after a step when there was no advance notice. False sends no customer emails for this rule. |
| `--notice-days` | int | Days before a step the customer is emailed, 0 to 180. 0 sends the email after the step instead. |
| `--active` | bool | Whether the rule still applies. Switching it off stops future steps on every contract using it; prices already applied and the history stay. |
| `--archived` | bool | Hides the rule from pickers. Contracts already using it keep working while Active is true. |

#### IndexationRule enum values

| Option | Valid values |
| ------ | ------------ |
| `--adjustment-type` | `1` Percentage, `2` FixedAmount |
| `--anchor-type` | `1` ContractAnniversary, `2` FixedDate |

<!-- END:GENERATED entity=IndexationRules -->
