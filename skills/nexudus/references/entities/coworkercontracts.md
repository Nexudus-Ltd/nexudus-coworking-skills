# CoworkerContracts

<!-- BEGIN:GENERATED entity=CoworkerContracts -->

A contract is a customer's plan agreement at a location. An active contract categorizes the customer as a Member; without one, they are a Contact. Its plan controls billing and can determine access, pricing, and eligibility for location services and inventory.

CoworkerContracts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkercontracts list --agent` | List all coworkercontracts |
| `nexudus coworkercontracts list --id <id> --agent` | Filter by single ID |
| `nexudus coworkercontracts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkercontracts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkercontracts list --coworker-full-name <value> --tariff-name <value> --agent` | Filter coworkercontracts by properties |
| `nexudus coworkercontracts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkercontracts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkercontracts get <id> --agent` | Get single coworkercontract |
| `nexudus coworkercontracts create --issued-by-id <value> --coworker-id <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create coworkercontract |
| `nexudus coworkercontracts update <id> --name "New Name" --agent` | Update coworkercontract |
| `nexudus coworkercontracts delete <id> --yes --agent` | Delete coworkercontract (no prompt) |

#### CoworkerContract list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long | ID of the location that issued this contract; it is supplied from the agent's current location context. |
| `--issued-by-name` | string | Name of the business issuing this contract |
| `--coworker-id` | long | ID of the customer this contract belongs to; a customer with an active contract is a Member, while one without an active contract is a Contact. |
| `--coworker-coworker-type` | string | The coworker coworker type value for this coworker contract |
| `--coworker-full-name` | string | Full name of the customer holding this contract |
| `--coworker-company-name` | string | Company name of the customer holding this contract |
| `--coworker-billing-name` | string | Billing name of the customer holding this contract |
| `--coworker-email` | string | Email address of the customer holding this contract |
| `--coworker-active` | bool | Whether coworker active is enabled |
| `--tariff-id` | long | ID of the plan assigned to this contract; its billing interval, price override rules, policies, and plan-based access or eligibility govern the customer. |
| `--tariff-name` | string | Name of the plan this contract is for |
| `--tariff-invoice-every` | int | The tariff invoice every value for this coworker contract |
| `--from-tariff-invoice-every` | range | |
| `--to-tariff-invoice-every` | range | |
| `--tariff-invoice-every-weeks` | int | The tariff invoice every weeks value for this coworker contract |
| `--from-tariff-invoice-every-weeks` | range | |
| `--to-tariff-invoice-every-weeks` | range | |
| `--tariff-price` | decimal | Default price of the plan. Used when the contract has no fixed Price override |
| `--from-tariff-price` | range | |
| `--to-tariff-price` | range | |
| `--tariff-currency-code` | string | Currency code of the plan |
| `--tariff-is-virtual-office` | bool | Whether the plan assigned to this contract is a virtual office plan |
| `--next-tariff-id` | long | ID of the plan scheduled to replace the current plan at a future renewal; leave empty when no change is scheduled. |
| `--next-tariff-name` | string | Name of the next plan the contract will switch to |
| `--notes` | string | Free-text internal notes about this customer contract. |
| `--start-date` | DateTime | Date when the contract begins; it is used to calculate billing and any minimum contract term. |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--billing-day` | int | Day of each month to bill this contract, from 1 through 28; scheduled monthly price changes must use this day. |
| `--from-billing-day` | range | |
| `--to-billing-day` | range | |
| `--renewal-date` | DateTime | System-calculated UTC date of the next plan invoice, derived from the plan, billing day, and cancellation settings. |
| `--from-renewal-date` | range | |
| `--to-renewal-date` | range | |
| `--invoiced-period` | DateTime | System-maintained UTC cutoff for the most recently invoiced contract period; do not set it manually. |
| `--from-invoiced-period` | range | |
| `--to-invoiced-period` | range | |
| `--price` | decimal | Optional per-unit price override for this contract; when empty, the assigned plan's price is used before applying quantity. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--value` | decimal | Optional per-unit contract value used for value calculations; when empty, the effective contract price is used. |
| `--from-value` | range | |
| `--to-value` | range | |
| `--quantity` | int | Number of plan units on the contract, at least 1; it multiplies price, included time, and contract value. |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--active` | bool | Whether the contract is currently active; this is system-managed status and cannot be changed directly. |
| `--main-contract` | bool | Whether this is the customer's main contract; use the dedicated set-main-contract action to change it. |
| `--cancelled` | bool | Whether the contract has been cancelled; use the dedicated cancellation action rather than changing this status. |
| `--purchase-order` | string | Customer purchase-order reference for this contract. |
| `--include-signup-fee` | bool | Whether the next eligible invoice includes the plan's sign-up fee. |
| `--invoice-advanced-cycles` | bool | Whether invoices include charges from future billing cycles when the plan permits them. |
| `--apply-pro-rating` | bool | Whether the contract's initial charges are prorated for a partial billing period. |
| `--price-plan-terms-accepted` | bool | Whether the customer accepted the assigned plan's terms and conditions. |
| `--price-plan-terms-accepted-on` | DateTime | Timestamp recorded when the customer accepted the plan terms; it is an audit value and cannot be changed directly. |
| `--from-price-plan-terms-accepted-on` | range | |
| `--to-price-plan-terms-accepted-on` | range | |
| `--cancellation-date` | DateTime | Optional UTC date on which the contract ends; cancellation policy and invoicing determine the earliest allowed date. |
| `--from-cancellation-date` | range | |
| `--to-cancellation-date` | range | |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice in days before the next billing day; when empty, the assigned plan's cancellation notice applies. |
| `--from-cancellation-limit-days` | range | |
| `--to-cancellation-limit-days` | range | |
| `--pro-rate-cancellation` | bool | Whether the cancellation invoice is prorated for the unused part of the billing period. |
| `--cancel-team-contracts` | bool | Whether cancelling this contract also cancels the customer's related team contracts. |
| `--cancellation-reason` | enum | Reason recorded for cancellation: PriceTooHigh, NewJobRelocation, MovedToOtherSpace, ChangeWorkEnvironment, LackCommunityInterations, PoorSpaceCondition, OtherMembers, Rellocated, BusinessExpansion, Pause, Renewed, Upgraded, Downgraded, Covid19, or Other. |
| `--cancellation-notes` | string | Free-text notes explaining the cancellation. |
| `--delivery-preference-checks` | enum | Preferred handling for delivered checks: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-mail` | enum | Preferred handling for delivered mail: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-parcels` | enum | Preferred handling for delivered parcels: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-publicity` | enum | Preferred handling for delivered publicity: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-instructions` | string | Free-text instructions for handling deliveries received for this contract. |
| `--identity-checks-due-on` | DateTime | Optional UTC date when identity verification is due for this contract. |
| `--from-identity-checks-due-on` | range | |
| `--to-identity-checks-due-on` | range | |
| `--address-checks-due-on` | DateTime | Optional UTC date when address verification is due for this contract. |
| `--from-address-checks-due-on` | range | |
| `--to-address-checks-due-on` | range | |
| `--floor-plan-desk-ids` | string | Read-only denormalized IDs of assigned floor-plan units; update Desks rather than this projection. |
| `--floor-plan-desk-names` | string | Read-only denormalized names of assigned floor-plan units; update Desks rather than this projection. |
| `--floor-plan-desk-variant-ids` | string | Read-only denormalized IDs of assigned floor-plan unit variants; update Variants rather than this projection. |
| `--floor-plan-desk-variant-names` | string | Read-only denormalized names of assigned floor-plan unit variants; update Variants rather than this projection. |
| `--po-box-number` | string | Post-office box number associated with this contract. |
| `--in-paused-period` | bool | Whether the contract is currently within a recorded pause period; it is calculated from pause-period records. |
| `--in-paused-period-from` | DateTime | Calculated UTC start of the active or upcoming pause period; manage pause records instead. |
| `--from-in-paused-period-from` | range | |
| `--to-in-paused-period-from` | range | |
| `--in-paused-period-until` | DateTime | Calculated UTC end of the active or upcoming pause period; manage pause records instead. |
| `--from-in-paused-period-until` | range | |
| `--to-in-paused-period-until` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerContract sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerContract create options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long, required | ID of the location that issued this contract; it is supplied from the agent's current location context. |
| `--coworker-id` | long, required | ID of the customer this contract belongs to; a customer with an active contract is a Member, while one without an active contract is a Contact. |
| `--tariff-id` | long, required | ID of the plan assigned to this contract; its billing interval, price override rules, policies, and plan-based access or eligibility govern the customer. |
| `--next-tariff-id` | long | ID of the plan scheduled to replace the current plan at a future renewal; leave empty when no change is scheduled. |
| `--notes` | string | Free-text internal notes about this customer contract. |
| `--start-date` | DateTime | Date when the contract begins; it is used to calculate billing and any minimum contract term. |
| `--billing-day` | int, required | Day of each month to bill this contract, from 1 through 28; scheduled monthly price changes must use this day. |
| `--renewal-date` | DateTime | System-calculated UTC date of the next plan invoice, derived from the plan, billing day, and cancellation settings. |
| `--invoiced-period` | DateTime | System-maintained UTC cutoff for the most recently invoiced contract period; do not set it manually. |
| `--price` | decimal | Optional per-unit price override for this contract; when empty, the assigned plan's price is used before applying quantity. |
| `--value` | decimal | Optional per-unit contract value used for value calculations; when empty, the effective contract price is used. |
| `--desks` | list, repeat flag | List of IDs of floor-plan units assigned to this contract; each unit must belong to a location the user can access. |
| `--added-desks` | list, repeat flag | The added desks value for this coworker contract |
| `--removed-desks` | list, repeat flag | The removed desks value for this coworker contract |
| `--variants` | list, repeat flag | List of IDs of floor-plan unit variants assigned to this contract; each variant's unit must belong to a location the user can access and connected to any of the desks/units associated with the contract. |
| `--added-variants` | list, repeat flag | The added variants value for this coworker contract |
| `--removed-variants` | list, repeat flag | The removed variants value for this coworker contract |
| `--quantity` | int, required | Number of plan units on the contract, at least 1; it multiplies price, included time, and contract value. |
| `--purchase-order` | string | Customer purchase-order reference for this contract. |
| `--include-signup-fee` | bool | Whether the next eligible invoice includes the plan's sign-up fee. |
| `--invoice-advanced-cycles` | bool | Whether invoices include charges from future billing cycles when the plan permits them. |
| `--apply-pro-rating` | bool | Whether the contract's initial charges are prorated for a partial billing period. |
| `--price-plan-terms-accepted` | bool | Whether the customer accepted the assigned plan's terms and conditions. |
| `--cancellation-date` | DateTime | Optional UTC date on which the contract ends; cancellation policy and invoicing determine the earliest allowed date. |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice in days before the next billing day; when empty, the assigned plan's cancellation notice applies. |
| `--pro-rate-cancellation` | bool | Whether the cancellation invoice is prorated for the unused part of the billing period. |
| `--cancel-team-contracts` | bool | Whether cancelling this contract also cancels the customer's related team contracts. |
| `--cancellation-reason` | enum | Reason recorded for cancellation: PriceTooHigh, NewJobRelocation, MovedToOtherSpace, ChangeWorkEnvironment, LackCommunityInterations, PoorSpaceCondition, OtherMembers, Rellocated, BusinessExpansion, Pause, Renewed, Upgraded, Downgraded, Covid19, or Other. |
| `--cancellation-notes` | string | Free-text notes explaining the cancellation. |
| `--delivery-preference-checks` | enum | Preferred handling for delivered checks: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-mail` | enum | Preferred handling for delivered mail: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-parcels` | enum | Preferred handling for delivered parcels: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-publicity` | enum | Preferred handling for delivered publicity: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-instructions` | string | Free-text instructions for handling deliveries received for this contract. |
| `--identity-checks-due-on` | DateTime | Optional UTC date when identity verification is due for this contract. |
| `--address-checks-due-on` | DateTime | Optional UTC date when address verification is due for this contract. |
| `--po-box-number` | string | Post-office box number associated with this contract. |
| `--contract-schedules` | JSON array or @filepath | Scheduled future price changes for this contract. Each entry sets a new Price to apply on a given date |

#### CoworkerContract update options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long | ID of the location that issued this contract; it is supplied from the agent's current location context. |
| `--coworker-id` | long | ID of the customer this contract belongs to; a customer with an active contract is a Member, while one without an active contract is a Contact. |
| `--tariff-id` | long | ID of the plan assigned to this contract; its billing interval, price override rules, policies, and plan-based access or eligibility govern the customer. |
| `--next-tariff-id` | long | ID of the plan scheduled to replace the current plan at a future renewal; leave empty when no change is scheduled. |
| `--notes` | string | Free-text internal notes about this customer contract. |
| `--start-date` | DateTime | Date when the contract begins; it is used to calculate billing and any minimum contract term. |
| `--billing-day` | int | Day of each month to bill this contract, from 1 through 28; scheduled monthly price changes must use this day. |
| `--renewal-date` | DateTime | System-calculated UTC date of the next plan invoice, derived from the plan, billing day, and cancellation settings. |
| `--invoiced-period` | DateTime | System-maintained UTC cutoff for the most recently invoiced contract period; do not set it manually. |
| `--price` | decimal | Optional per-unit price override for this contract; when empty, the assigned plan's price is used before applying quantity. |
| `--value` | decimal | Optional per-unit contract value used for value calculations; when empty, the effective contract price is used. |
| `--desks` | list, repeat flag | List of IDs of floor-plan units assigned to this contract; each unit must belong to a location the user can access. |
| `--added-desks` | list, repeat flag | The added desks value for this coworker contract |
| `--removed-desks` | list, repeat flag | The removed desks value for this coworker contract |
| `--variants` | list, repeat flag | List of IDs of floor-plan unit variants assigned to this contract; each variant's unit must belong to a location the user can access and connected to any of the desks/units associated with the contract. |
| `--added-variants` | list, repeat flag | The added variants value for this coworker contract |
| `--removed-variants` | list, repeat flag | The removed variants value for this coworker contract |
| `--quantity` | int | Number of plan units on the contract, at least 1; it multiplies price, included time, and contract value. |
| `--purchase-order` | string | Customer purchase-order reference for this contract. |
| `--include-signup-fee` | bool | Whether the next eligible invoice includes the plan's sign-up fee. |
| `--invoice-advanced-cycles` | bool | Whether invoices include charges from future billing cycles when the plan permits them. |
| `--apply-pro-rating` | bool | Whether the contract's initial charges are prorated for a partial billing period. |
| `--price-plan-terms-accepted` | bool | Whether the customer accepted the assigned plan's terms and conditions. |
| `--cancellation-date` | DateTime | Optional UTC date on which the contract ends; cancellation policy and invoicing determine the earliest allowed date. |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice in days before the next billing day; when empty, the assigned plan's cancellation notice applies. |
| `--pro-rate-cancellation` | bool | Whether the cancellation invoice is prorated for the unused part of the billing period. |
| `--cancel-team-contracts` | bool | Whether cancelling this contract also cancels the customer's related team contracts. |
| `--cancellation-reason` | enum | Reason recorded for cancellation: PriceTooHigh, NewJobRelocation, MovedToOtherSpace, ChangeWorkEnvironment, LackCommunityInterations, PoorSpaceCondition, OtherMembers, Rellocated, BusinessExpansion, Pause, Renewed, Upgraded, Downgraded, Covid19, or Other. |
| `--cancellation-notes` | string | Free-text notes explaining the cancellation. |
| `--delivery-preference-checks` | enum | Preferred handling for delivered checks: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-mail` | enum | Preferred handling for delivered mail: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-parcels` | enum | Preferred handling for delivered parcels: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-preference-publicity` | enum | Preferred handling for delivered publicity: StoreForCollection, Forward, OpenScanForward, OpenScanRecycle, OpenScanShred, OpenScanStoreForCollection, Recycle, ReturnToSender, Shred, DepositCheck, or Unknown. |
| `--delivery-instructions` | string | Free-text instructions for handling deliveries received for this contract. |
| `--identity-checks-due-on` | DateTime | Optional UTC date when identity verification is due for this contract. |
| `--address-checks-due-on` | DateTime | Optional UTC date when address verification is due for this contract. |
| `--po-box-number` | string | Post-office box number associated with this contract. |
| `--contract-schedules` | JSON array or @filepath | Scheduled future price changes for this contract. Each entry sets a new Price to apply on a given date |

#### CoworkerContract PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus coworkercontracts update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### CoworkerContract (key fields)

`Id`, `CoworkerFullName`, `TariffName`, `StartDate`, `Price`, `Active`, `Cancelled`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`

#### CoworkerContract inline children

CoworkerContract supports inline child objects on create and update. Pass a JSON array or a `@filepath` reference.

**`--contract-schedules`** — Scheduled future price changes for this contract. Each entry sets a new Price to apply on a given date

Writable properties: `Price`, `ApplyOn`

```shell
nexudus coworkercontracts create ... --contract-schedules '[{"Price": 10.00, "ApplyOn": "..."}]' --agent
```

Or from a file:

```shell
nexudus coworkercontracts create ... --contract-schedules @contractschedules.json --agent
```

<!-- END:GENERATED entity=CoworkerContracts -->
