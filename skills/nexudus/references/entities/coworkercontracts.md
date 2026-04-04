# CoworkerContracts

<!-- BEGIN:GENERATED entity=CoworkerContracts -->

A **CoworkerContract** is the foundation for automatic billing. It links a customer (`Coworker`) to a plan (`Tariff`) that drives the billing frequency, benefits and default settings for the contract. A customer can hold as many contracts as needed, each pointing to the same or different plans.

A customer with at least one active contract is regarded as a **Member**; customers with no active contracts are **Contacts**. Nexudus uses this distinction to enforce policies on products, resources, events, pricing and many other entities that expose `OnlyForMembers` or `OnlyForContacts` properties.

**Pricing** — The contract price can be fixed (`Price` is not null) or derived from the plan it is for. The `Value` field is used in reporting to compare with the actual price. Automatic price adjustments over time can be set up via `ContractSchedule` child entities.

**Billing cycle** — `RenewalDate` is the date on which the contract will next be automatically invoiced; it advances automatically each time the contract is invoiced. `InvoicedPeriod` is the period the next invoice will cover. For a new contract these two dates are usually the same. If `Tariff.AdvanceInvoiceCycles` is greater than 1, Nexudus invoices several periods in one go the first time, pushing `InvoicedPeriod` ahead of `RenewalDate` from the first invoice onwards. When the contract is cancelled, Nexudus stops invoicing once `InvoicedPeriod` reaches the cancellation date.

**Benefits** — The plan may include benefits (booking credits, time passes, etc.) which are released and assigned to the contract-holder customer based on the contract cycle or other expiration criteria (month, week, day, etc.).

**Cancellation** — Contracts support minimum contract length (`ContractTerm`), cancellation policies (`CancellationLimitDays`, `ProRateCancellation`) and cancellation reasons. `CancelTeamContracts` can cascade cancellation to team members.

**Additional charges** — Contracts can optionally include products (`ContractProduct` entities) to be billed alongside the plan, as well as security deposits/retainers (`ContractDeposit` entities).

CoworkerContracts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkercontracts list --agent` | List all coworkercontracts |
| `nexudus coworkercontracts list --id <id> --agent` | Filter by single ID |
| `nexudus coworkercontracts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkercontracts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkercontracts list --start-date <value> --price <value> --agent` | Filter coworkercontracts by properties |
| `nexudus coworkercontracts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkercontracts get <id> --agent` | Get single coworkercontract |
| `nexudus coworkercontracts create --issued-by-id <value> --coworker-id <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create coworkercontract |
| `nexudus coworkercontracts update <id> --name "New Name" --agent` | Update coworkercontract |
| `nexudus coworkercontracts delete <id> --yes --agent` | Delete coworkercontract (no prompt) |

#### CoworkerContract list filter options

`--issued-by-id`, `--coworker-id`, `--tariff-id`, `--next-tariff-id`, `--notes`, `--start-date`, `--billing-day`, `--renewal-date`, `--invoiced-period`, `--contract-term`, `--price`, `--value`, `--quantity`, `--purchase-order`, `--include-signup-fee`, `--invoice-advanced-cycles`, `--apply-pro-rating`, `--next-auto-invoice`, `--price-plan-terms-accepted`, `--cancellation-date`, `--cancellation-limit-days`, `--pro-rate-cancellation`, `--cancel-team-contracts`, `--cancellation-reason`, `--cancellation-notes`, `--delivery-preference-checks`, `--delivery-preference-mail`, `--delivery-preference-parcels`, `--delivery-preference-publicity`, `--delivery-instructions`, `--identity-checks-due-on`, `--address-checks-due-on`, `--start-date-local`, `--renewal-date-local`, `--next-auto-invoice-local`, `--price-plan-terms-accepted-on-local`, `--cancellation-date-local`, `--contract-term-local`, `--invoiced-period-local`, `--po-box-number`

#### CoworkerContract create options

`--issued-by-id` (required), `--coworker-id` (required), `--tariff-id` (required), `--next-tariff-id`, `--notes`, `--start-date`, `--billing-day` (required), `--renewal-date`, `--invoiced-period`, `--contract-term`, `--price`, `--value`, `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--variants` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--quantity` (required), `--purchase-order`, `--include-signup-fee`, `--invoice-advanced-cycles`, `--apply-pro-rating`, `--next-auto-invoice`, `--price-plan-terms-accepted`, `--cancellation-date`, `--cancellation-limit-days`, `--pro-rate-cancellation`, `--cancel-team-contracts`, `--cancellation-reason`, `--cancellation-notes`, `--deposits` (list, repeat flag), `--added-deposits` (list, repeat flag), `--removed-deposits` (list, repeat flag), `--contacts` (list, repeat flag), `--added-contacts` (list, repeat flag), `--removed-contacts` (list, repeat flag), `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--schedules` (list, repeat flag), `--added-schedules` (list, repeat flag), `--removed-schedules` (list, repeat flag), `--paused-periods` (list, repeat flag), `--added-paused-periods` (list, repeat flag), `--removed-paused-periods` (list, repeat flag), `--delivery-preference-checks`, `--delivery-preference-mail`, `--delivery-preference-parcels`, `--delivery-preference-publicity`, `--delivery-instructions`, `--identity-checks-due-on`, `--address-checks-due-on`, `--start-date-local`, `--renewal-date-local`, `--next-auto-invoice-local`, `--price-plan-terms-accepted-on-local`, `--cancellation-date-local`, `--contract-term-local`, `--invoiced-period-local`, `--po-box-number`, `--contract-schedules` (JSON array or @filepath)

#### CoworkerContract update options

`--issued-by-id`, `--coworker-id`, `--tariff-id`, `--next-tariff-id`, `--notes`, `--start-date`, `--billing-day`, `--renewal-date`, `--invoiced-period`, `--contract-term`, `--price`, `--value`, `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--variants` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--quantity`, `--purchase-order`, `--include-signup-fee`, `--invoice-advanced-cycles`, `--apply-pro-rating`, `--next-auto-invoice`, `--price-plan-terms-accepted`, `--cancellation-date`, `--cancellation-limit-days`, `--pro-rate-cancellation`, `--cancel-team-contracts`, `--cancellation-reason`, `--cancellation-notes`, `--deposits` (list, repeat flag), `--added-deposits` (list, repeat flag), `--removed-deposits` (list, repeat flag), `--contacts` (list, repeat flag), `--added-contacts` (list, repeat flag), `--removed-contacts` (list, repeat flag), `--products` (list, repeat flag), `--added-products` (list, repeat flag), `--removed-products` (list, repeat flag), `--schedules` (list, repeat flag), `--added-schedules` (list, repeat flag), `--removed-schedules` (list, repeat flag), `--paused-periods` (list, repeat flag), `--added-paused-periods` (list, repeat flag), `--removed-paused-periods` (list, repeat flag), `--delivery-preference-checks`, `--delivery-preference-mail`, `--delivery-preference-parcels`, `--delivery-preference-publicity`, `--delivery-instructions`, `--identity-checks-due-on`, `--address-checks-due-on`, `--start-date-local`, `--renewal-date-local`, `--next-auto-invoice-local`, `--price-plan-terms-accepted-on-local`, `--cancellation-date-local`, `--contract-term-local`, `--invoiced-period-local`, `--po-box-number`, `--contract-schedules` (JSON array or @filepath)

### CoworkerContract (key fields)

`Id`, `CoworkerFullName`, `TariffName`, `StartDate`, `Price`, `Active`, `Cancelled`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`, `Deposits`, `AddedDeposits`, `RemovedDeposits`, `Contacts`, `AddedContacts`, `RemovedContacts`, `Products`, `AddedProducts`, `RemovedProducts`, `Schedules`, `AddedSchedules`, `RemovedSchedules`, `PausedPeriods`, `AddedPausedPeriods`, `RemovedPausedPeriods`

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
