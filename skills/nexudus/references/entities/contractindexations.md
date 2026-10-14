# ContractIndexations

<!-- BEGIN:GENERATED entity=ContractIndexations -->

A ContractIndexation is one applied step of an IndexationRule on a customer contract: the date it became effective, the unit price before and after, the adjustment used and whether this was the step that gave the contract its own price instead of the plan price. The bill run writes one row per step when it raises the invoice for the first period at the new price. Filter by coworkerContract_id for a contract's history or by indexationRule_id for everything a rule did. Rows cannot be created, edited or deleted here; change the contract or the rule instead.

ContractIndexations support Search, Get, Create, Update (no Delete via API).

| Command | Description |
| --- | --- |
| `nexudus contractindexations list --agent` | List all contractindexations |
| `nexudus contractindexations list --id <id> --agent` | Filter by single ID |
| `nexudus contractindexations list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractindexations list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractindexations list --coworker-contract-id <value> --coworker-contract-quantity <value> --agent` | Filter contractindexations by properties |
| `nexudus contractindexations list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractindexations list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus contractindexations get <id> --agent` | Get single contractindexation |
| `nexudus contractindexations create  --agent` | Create contractindexation |
| `nexudus contractindexations update <id> --name "New Name" --agent` | Update contractindexation |

#### ContractIndexation list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the contract whose unit price this step changed. |
| `--coworker-contract-quantity` | int | Display value for CoworkerContract.Quantity. |
| `--from-coworker-contract-quantity` | range | |
| `--to-coworker-contract-quantity` | range | |
| `--coworker-contract-price` | decimal | Display value for CoworkerContract.Price. |
| `--from-coworker-contract-price` | range | |
| `--to-coworker-contract-price` | range | |
| `--coworker-contract-tariff-name` | string | Display value for CoworkerContract.Tariff.Name. |
| `--coworker-contract-coworker-id` | int | Display value for CoworkerContract.Coworker.Id. |
| `--from-coworker-contract-coworker-id` | range | |
| `--to-coworker-contract-coworker-id` | range | |
| `--coworker-contract-coworker-full-name` | string | Display value for CoworkerContract.Coworker.FullName. |
| `--coworker-contract-issued-by-id` | int | Display value for CoworkerContract.IssuedBy.Id. |
| `--from-coworker-contract-issued-by-id` | range | |
| `--to-coworker-contract-issued-by-id` | range | |
| `--coworker-contract-issued-by-name` | string | Display value for CoworkerContract.IssuedBy.Name. |
| `--indexation-rule-id` | long | ID of the rule that produced the step. Empty when the rule was deleted afterwards; RuleName keeps its name. |
| `--indexation-rule-name` | string | Display value for IndexationRule.Name. |
| `--rule-name` | string | Name of the rule when the step applied. |
| `--effective-on` | DateTime | Step date, UTC midnight of the business-local day. The new price bills from the first period starting on or after it. |
| `--from-effective-on` | range | |
| `--to-effective-on` | range | |
| `--effective-on-local` | DateTime | Business-local date and time of EffectiveOn. |
| `--from-effective-on-local` | range | |
| `--to-effective-on-local` | range | |
| `--applied-on` | DateTime | UTC moment the bill run applied the step to the contract. |
| `--from-applied-on` | range | |
| `--to-applied-on` | range | |
| `--period-start` | DateTime | Start of the first billing period charged at the new price (UTC). |
| `--from-period-start` | range | |
| `--to-period-start` | range | |
| `--previous-price` | decimal | Unit price before the step. When the contract was following its plan price this is the plan price at the time. |
| `--from-previous-price` | range | |
| `--to-previous-price` | range | |
| `--new-price` | decimal | Unit price after the step, which is the contract unit price override from then on. |
| `--from-new-price` | range | |
| `--to-new-price` | range | |
| `--adjustment-type` | enum | Adjustment type of the rule when the step applied. |
| `--amount` | decimal | Percent or amount per unit applied by the step. |
| `--from-amount` | range | |
| `--to-amount` | range | |
| `--rounding-increment` | decimal | Rounding increment used by the step. Empty means 0.01. |
| `--from-rounding-increment` | range | |
| `--to-rounding-increment` | range | |
| `--was-following-plan-price` | bool | True on the step that gave the contract its own unit price. Before it the contract followed its plan price; after it the contract no longer follows plan price changes. |
| `--products-adjusted` | bool | True when the rule also adjusted the contract products in this step. |
| `--previous-products-total` | decimal | Sum of the contract product unit prices before the step, when products were adjusted. |
| `--from-previous-products-total` | range | |
| `--to-previous-products-total` | range | |
| `--new-products-total` | decimal | Sum of the contract product unit prices after the step, when products were adjusted. |
| `--from-new-products-total` | range | |
| `--to-new-products-total` | range | |
| `--coworker-invoice-unique-id` | string | Unique id of the invoice that first billed the new price, once it was saved. |
| `--customer-notified-on` | DateTime | UTC moment the customer was told about this step (advance notice or applied email). Empty until the daily notices task processes it. |
| `--from-customer-notified-on` | range | |
| `--to-customer-notified-on` | range | |
| `--notes` | string | Free text, for example that several overdue steps were applied together. |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractIndexation sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` descending. If no `--order-by` is specified, the API returns results ordered by `Id` (descending).

#### ContractIndexation create options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string | Free text, for example that several overdue steps were applied together. |

#### ContractIndexation update options

| Option | Type | Description |
| --- | --- | --- |
| `--notes` | string | Free text, for example that several overdue steps were applied together. |

#### ContractIndexation PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-contract-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus contractindexations update <id> --coworker-contract-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

<!-- END:GENERATED entity=ContractIndexations -->
