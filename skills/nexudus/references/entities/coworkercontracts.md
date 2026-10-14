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
| `--issued-by-name` | string | Display value for IssuedBy.Name. |
| `--coworker-id` | long | ID of the customer this contract belongs to; a customer with an active contract is a Member, while one without an active contract is a Contact. |
| `--coworker-coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--coworker-email` | string | Display value for Coworker.Email. |
| `--coworker-active` | bool | Display value for Coworker.Active. |
| `--tariff-id` | long | ID of the plan assigned to this contract; its billing interval, price override rules, policies, and plan-based access or eligibility govern the customer. |
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
| `--tariff-currency-code` | string | Display value for Tariff.Currency.Code. |
| `--tariff-is-virtual-office` | bool | Display value for Tariff.IsVirtualOffice. |
| `--next-tariff-id` | long | ID of the plan scheduled to replace the current plan at a future renewal; leave empty when no change is scheduled. |
| `--next-tariff-name` | string | Display value for NextTariff.Name. |
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
| `--contract-term` | DateTime | System-calculated UTC end of the minimum contract term; change the plan or start date instead. |
| `--from-contract-term` | range | |
| `--to-contract-term` | range | |
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
| `--proposal-unique-id` | string | Integration-managed identifier of the source proposal; it is read-only and cannot be changed through contract administration. |
| `--proposal-contract-unique-id` | string | Integration-managed identifier of the related proposal contract; it is read-only and cannot be changed through contract administration. |
| `--course-member-unique-id` | string | Integration-managed identifier of the related course member; it is read-only and cannot be changed through contract administration. |
| `--floor-plan-desk-ids` | string | Read-only denormalized IDs of assigned floor-plan units; update Desks rather than this projection. |
| `--floor-plan-desk-names` | string | Read-only denormalized names of assigned floor-plan units; update Desks rather than this projection. |
| `--floor-plan-desk-variant-ids` | string | Read-only denormalized IDs of assigned floor-plan unit variants; update Variants rather than this projection. |
| `--floor-plan-desk-variant-names` | string | Read-only denormalized names of assigned floor-plan unit variants; update Variants rather than this projection. |
| `--price-with-products-and-deposits` | decimal | System-calculated total including the contract price, products, deposits, and quantity; update the contributing records instead. |
| `--from-price-with-products-and-deposits` | range | |
| `--to-price-with-products-and-deposits` | range | |
| `--price-with-products` | decimal | System-calculated total including the contract price, products, and quantity; update the contributing records instead. |
| `--from-price-with-products` | range | |
| `--to-price-with-products` | range | |
| `--po-box-number` | string | Post-office box number associated with this contract. |
| `--in-paused-period` | bool | Whether the contract is currently within a recorded pause period; it is calculated from pause-period records. |
| `--in-paused-period-from` | DateTime | Calculated UTC start of the active or upcoming pause period; manage pause records instead. |
| `--from-in-paused-period-from` | range | |
| `--to-in-paused-period-from` | range | |
| `--in-paused-period-until` | DateTime | Calculated UTC end of the active or upcoming pause period; manage pause records instead. |
| `--from-in-paused-period-until` | range | |
| `--to-in-paused-period-until` | range | |
| `--indexation-rule-id` | long | ID of the indexation rule that steps this contract's unit price on each step date for as long as the contract is active. The rule can belong to any location. The first step copies the plan price into the contract's own unit price when it had none, and the contract then no longer follows plan price changes. A contract with a unit price override cannot schedule a different next plan. |
| `--indexation-rule-name` | string | Display value for IndexationRule.Name. |
| `--indexation-rule-adjustment-type` | string | Display value for IndexationRule.AdjustmentType. |
| `--indexation-rule-amount` | decimal | Display value for IndexationRule.Amount. |
| `--from-indexation-rule-amount` | range | |
| `--to-indexation-rule-amount` | range | |
| `--indexation-rule-rounding-increment` | decimal | Display value for IndexationRule.RoundingIncrement. |
| `--from-indexation-rule-rounding-increment` | range | |
| `--to-indexation-rule-rounding-increment` | range | |
| `--indexation-rule-anchor-type` | string | Display value for IndexationRule.AnchorType. |
| `--indexation-rule-anchor-month` | int | Display value for IndexationRule.AnchorMonth. |
| `--from-indexation-rule-anchor-month` | range | |
| `--to-indexation-rule-anchor-month` | range | |
| `--indexation-rule-anchor-day` | int | Display value for IndexationRule.AnchorDay. |
| `--from-indexation-rule-anchor-day` | range | |
| `--to-indexation-rule-anchor-day` | range | |
| `--indexation-rule-frequency-months` | int | Display value for IndexationRule.FrequencyMonths. |
| `--from-indexation-rule-frequency-months` | range | |
| `--to-indexation-rule-frequency-months` | range | |
| `--indexation-rule-minimum-months-before-first` | int | Display value for IndexationRule.MinimumMonthsBeforeFirst. |
| `--from-indexation-rule-minimum-months-before-first` | range | |
| `--to-indexation-rule-minimum-months-before-first` | range | |
| `--indexation-rule-apply-to-contract-products` | bool | Display value for IndexationRule.ApplyToContractProducts. |
| `--indexation-rule-active` | bool | Display value for IndexationRule.Active. |
| `--next-indexation-on` | DateTime | Date of the next indexation step (UTC midnight of the business-local day), maintained by the system from the rule and the contract start. Empty when the contract has no active rule. |
| `--from-next-indexation-on` | range | |
| `--to-next-indexation-on` | range | |
| `--next-indexation-on-local` | DateTime | Business-local date and time of NextIndexationOn. |
| `--from-next-indexation-on-local` | range | |
| `--to-next-indexation-on-local` | range | |
| `--last-indexation-on` | DateTime | Effective date of the last indexation step applied to this contract. |
| `--from-last-indexation-on` | range | |
| `--to-last-indexation-on` | range | |
| `--last-indexation-on-local` | DateTime | Business-local date and time of LastIndexationOn. |
| `--from-last-indexation-on-local` | range | |
| `--to-last-indexation-on-local` | range | |
| `--indexation-count` | int | Number of indexation steps applied to this contract so far. |
| `--from-indexation-count` | range | |
| `--to-indexation-count` | range | |
| `--price-set-by` | enum | Who last wrote the unit price override: Operator (edited by hand), Schedule (a price schedule applied) or Indexation (an indexation step applied). Empty while the contract follows its plan price. |
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
| `--contract-term` | DateTime | System-calculated UTC end of the minimum contract term; change the plan or start date instead. |
| `--price` | decimal | Optional per-unit price override for this contract; when empty, the assigned plan's price is used before applying quantity. |
| `--value` | decimal | Optional per-unit contract value used for value calculations; when empty, the effective contract price is used. |
| `--desks` | list, repeat flag | List of IDs of floor-plan units assigned to this contract; each unit must belong to a location the user can access. |
| `--added-desks` | list, repeat flag | IDs added to the Desks relationship. |
| `--removed-desks` | list, repeat flag | IDs removed from the Desks relationship. |
| `--variants` | list, repeat flag | List of IDs of floor-plan unit variants assigned to this contract; each variant's unit must belong to a location the user can access and connected to any of the desks/units associated with the contract. |
| `--added-variants` | list, repeat flag | IDs added to the Variants relationship. |
| `--removed-variants` | list, repeat flag | IDs removed from the Variants relationship. |
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
| `--indexation-rule-id` | long | ID of the indexation rule that steps this contract's unit price on each step date for as long as the contract is active. The rule can belong to any location. The first step copies the plan price into the contract's own unit price when it had none, and the contract then no longer follows plan price changes. A contract with a unit price override cannot schedule a different next plan. |
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
| `--contract-term` | DateTime | System-calculated UTC end of the minimum contract term; change the plan or start date instead. |
| `--price` | decimal | Optional per-unit price override for this contract; when empty, the assigned plan's price is used before applying quantity. |
| `--value` | decimal | Optional per-unit contract value used for value calculations; when empty, the effective contract price is used. |
| `--desks` | list, repeat flag | List of IDs of floor-plan units assigned to this contract; each unit must belong to a location the user can access. |
| `--added-desks` | list, repeat flag | IDs added to the Desks relationship. |
| `--removed-desks` | list, repeat flag | IDs removed from the Desks relationship. |
| `--variants` | list, repeat flag | List of IDs of floor-plan unit variants assigned to this contract; each variant's unit must belong to a location the user can access and connected to any of the desks/units associated with the contract. |
| `--added-variants` | list, repeat flag | IDs added to the Variants relationship. |
| `--removed-variants` | list, repeat flag | IDs removed from the Variants relationship. |
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
| `--indexation-rule-id` | long | ID of the indexation rule that steps this contract's unit price on each step date for as long as the contract is active. The rule can belong to any location. The first step copies the plan price into the contract's own unit price when it had none, and the contract then no longer follows plan price changes. A contract with a unit price override cannot schedule a different next plan. |
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
