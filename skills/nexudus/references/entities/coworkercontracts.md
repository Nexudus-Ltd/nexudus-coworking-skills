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
| `nexudus coworkercontracts list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkercontracts get <id> --agent` | Get single coworkercontract |
| `nexudus coworkercontracts create --issued-by-id <value> --coworker-id <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create coworkercontract |
| `nexudus coworkercontracts update <id> --name "New Name" --agent` | Update coworkercontract |
| `nexudus coworkercontracts delete <id> --yes --agent` | Delete coworkercontract (no prompt) |

#### CoworkerContract list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long | ID of the issued by linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--next-tariff-id` | long | ID of the next tariff linked to this record |
| `--notes` | string | Free-text notes for this contract |
| `--start-date` | DateTime | Contract start date |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--billing-day` | int | Day of month on which billing occurs |
| `--from-billing-day` | range | |
| `--to-billing-day` | range | |
| `--renewal-date` | DateTime | Date on which the contract will next be automatically invoiced. Updated automatically every time the contract is invoiced, advancing by the plan's renewal period |
| `--from-renewal-date` | range | |
| `--to-renewal-date` | range | |
| `--invoiced-period` | DateTime | Period the next invoice will cover. For new contracts this equals RenewalDate. If Tariff.AdvanceInvoiceCycles > 1, Nexudus invoices several periods at once on the first invoice, pushing InvoicedPeriod ahead of RenewalDate. Nexudus stops invoicing when InvoicedPeriod reaches the cancellation date |
| `--from-invoiced-period` | range | |
| `--to-invoiced-period` | range | |
| `--contract-term` | DateTime | Minimum contract length end date. Defines the earliest date at which the contract can be cancelled without penalty |
| `--from-contract-term` | range | |
| `--to-contract-term` | range | |
| `--price` | decimal | Fixed price override for this contract. If null, the contract uses the plan's default price (TariffPrice) |
| `--from-price` | range | |
| `--to-price` | range | |
| `--value` | decimal | Contract value used in reporting to compare against the actual invoiced price |
| `--from-value` | range | |
| `--to-value` | range | |
| `--quantity` | int | Number of units |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--purchase-order` | string | Purchase order |
| `--include-signup-fee` | bool | Whether to include the plan's signup fee when creating this contract |
| `--invoice-advanced-cycles` | bool | Whether to invoice multiple billing cycles in advance on the first invoice, as configured by Tariff.AdvanceInvoiceCycles |
| `--apply-pro-rating` | bool | Whether to pro-rate the first invoice based on the contract start date relative to the billing cycle |
| `--next-auto-invoice` | DateTime | Date of the next automatic invoice generation for this contract |
| `--from-next-auto-invoice` | range | |
| `--to-next-auto-invoice` | range | |
| `--price-plan-terms-accepted` | bool | Whether the customer has accepted the plan's terms and conditions |
| `--cancellation-date` | DateTime | Date on which the contract will be cancelled. Nexudus stops invoicing when InvoicedPeriod reaches this date |
| `--from-cancellation-date` | range | |
| `--to-cancellation-date` | range | |
| `--cancellation-limit-days` | int | Minimum number of days' notice required before cancellation takes effect |
| `--from-cancellation-limit-days` | range | |
| `--to-cancellation-limit-days` | range | |
| `--pro-rate-cancellation` | bool | Whether to pro-rate the final invoice when the contract is cancelled mid-cycle |
| `--cancel-team-contracts` | bool | Whether to cascade cancellation to contracts of team members under this customer |
| `--cancellation-reason` | enum | Reason for cancellation |
| `--cancellation-notes` | string | Free-text notes about the cancellation |
| `--delivery-preference-checks` | enum | Delivery handling preference for checks |
| `--delivery-preference-mail` | enum | Delivery handling preference for mail |
| `--delivery-preference-parcels` | enum | Delivery handling preference for parcels |
| `--delivery-preference-publicity` | enum | Delivery handling preference for publicity |
| `--delivery-instructions` | string | Free-text delivery instructions for this contract's mail handling |
| `--identity-checks-due-on` | DateTime | Date by which identity verification checks must be completed for this contract |
| `--from-identity-checks-due-on` | range | |
| `--to-identity-checks-due-on` | range | |
| `--address-checks-due-on` | DateTime | Date by which address verification checks must be completed for this contract |
| `--from-address-checks-due-on` | range | |
| `--to-address-checks-due-on` | range | |
| `--start-date-local` | DateTime | Date/time value for start date local |
| `--from-start-date-local` | range | |
| `--to-start-date-local` | range | |
| `--renewal-date-local` | DateTime | Date/time value for renewal date local |
| `--from-renewal-date-local` | range | |
| `--to-renewal-date-local` | range | |
| `--next-auto-invoice-local` | DateTime | Date/time value for next auto invoice local |
| `--from-next-auto-invoice-local` | range | |
| `--to-next-auto-invoice-local` | range | |
| `--price-plan-terms-accepted-on-local` | DateTime | Date/time value for price plan terms accepted on local |
| `--from-price-plan-terms-accepted-on-local` | range | |
| `--to-price-plan-terms-accepted-on-local` | range | |
| `--cancellation-date-local` | DateTime | Date/time value for cancellation date local |
| `--from-cancellation-date-local` | range | |
| `--to-cancellation-date-local` | range | |
| `--contract-term-local` | DateTime | Date/time value for contract term local |
| `--from-contract-term-local` | range | |
| `--to-contract-term-local` | range | |
| `--invoiced-period-local` | DateTime | Date/time value for invoiced period local |
| `--from-invoiced-period-local` | range | |
| `--to-invoiced-period-local` | range | |
| `--po-box-number` | string | PO box number |
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
| `--issued-by-id` | long, required | ID of the issued by linked to this record |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--tariff-id` | long, required | ID of the tariff linked to this record |
| `--next-tariff-id` | long | ID of the next tariff linked to this record |
| `--notes` | string | Free-text notes for this contract |
| `--start-date` | DateTime | Contract start date |
| `--billing-day` | int, required | Day of month on which billing occurs |
| `--renewal-date` | DateTime | Date on which the contract will next be automatically invoiced. Updated automatically every time the contract is invoiced, advancing by the plan's renewal period |
| `--invoiced-period` | DateTime | Period the next invoice will cover. For new contracts this equals RenewalDate. If Tariff.AdvanceInvoiceCycles > 1, Nexudus invoices several periods at once on the first invoice, pushing InvoicedPeriod ahead of RenewalDate. Nexudus stops invoicing when InvoicedPeriod reaches the cancellation date |
| `--contract-term` | DateTime | Minimum contract length end date. Defines the earliest date at which the contract can be cancelled without penalty |
| `--price` | decimal | Fixed price override for this contract. If null, the contract uses the plan's default price (TariffPrice) |
| `--value` | decimal | Contract value used in reporting to compare against the actual invoiced price |
| `--desks` | list, repeat flag | List of desks linked to this record |
| `--added-desks` | list, repeat flag | The added desks value for this coworker contract |
| `--removed-desks` | list, repeat flag | The removed desks value for this coworker contract |
| `--variants` | list, repeat flag | List of variants linked to this record |
| `--added-variants` | list, repeat flag | The added variants value for this coworker contract |
| `--removed-variants` | list, repeat flag | The removed variants value for this coworker contract |
| `--quantity` | int, required | Number of units |
| `--purchase-order` | string | Purchase order |
| `--include-signup-fee` | bool | Whether to include the plan's signup fee when creating this contract |
| `--invoice-advanced-cycles` | bool | Whether to invoice multiple billing cycles in advance on the first invoice, as configured by Tariff.AdvanceInvoiceCycles |
| `--apply-pro-rating` | bool | Whether to pro-rate the first invoice based on the contract start date relative to the billing cycle |
| `--next-auto-invoice` | DateTime | Date of the next automatic invoice generation for this contract |
| `--price-plan-terms-accepted` | bool | Whether the customer has accepted the plan's terms and conditions |
| `--cancellation-date` | DateTime | Date on which the contract will be cancelled. Nexudus stops invoicing when InvoicedPeriod reaches this date |
| `--cancellation-limit-days` | int | Minimum number of days' notice required before cancellation takes effect |
| `--pro-rate-cancellation` | bool | Whether to pro-rate the final invoice when the contract is cancelled mid-cycle |
| `--cancel-team-contracts` | bool | Whether to cascade cancellation to contracts of team members under this customer |
| `--cancellation-reason` | enum | Reason for cancellation |
| `--cancellation-notes` | string | Free-text notes about the cancellation |
| `--delivery-preference-checks` | enum | Delivery handling preference for checks |
| `--delivery-preference-mail` | enum | Delivery handling preference for mail |
| `--delivery-preference-parcels` | enum | Delivery handling preference for parcels |
| `--delivery-preference-publicity` | enum | Delivery handling preference for publicity |
| `--delivery-instructions` | string | Free-text delivery instructions for this contract's mail handling |
| `--identity-checks-due-on` | DateTime | Date by which identity verification checks must be completed for this contract |
| `--address-checks-due-on` | DateTime | Date by which address verification checks must be completed for this contract |
| `--start-date-local` | DateTime | Date/time value for start date local |
| `--renewal-date-local` | DateTime | Date/time value for renewal date local |
| `--next-auto-invoice-local` | DateTime | Date/time value for next auto invoice local |
| `--price-plan-terms-accepted-on-local` | DateTime | Date/time value for price plan terms accepted on local |
| `--cancellation-date-local` | DateTime | Date/time value for cancellation date local |
| `--contract-term-local` | DateTime | Date/time value for contract term local |
| `--invoiced-period-local` | DateTime | Date/time value for invoiced period local |
| `--po-box-number` | string | PO box number |
| `--contract-schedules` | JSON array or @filepath | Scheduled future price changes for this contract. Each entry sets a new Price to apply on a given date |

#### CoworkerContract update options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long | ID of the issued by linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--tariff-id` | long | ID of the tariff linked to this record |
| `--next-tariff-id` | long | ID of the next tariff linked to this record |
| `--notes` | string | Free-text notes for this contract |
| `--start-date` | DateTime | Contract start date |
| `--billing-day` | int | Day of month on which billing occurs |
| `--renewal-date` | DateTime | Date on which the contract will next be automatically invoiced. Updated automatically every time the contract is invoiced, advancing by the plan's renewal period |
| `--invoiced-period` | DateTime | Period the next invoice will cover. For new contracts this equals RenewalDate. If Tariff.AdvanceInvoiceCycles > 1, Nexudus invoices several periods at once on the first invoice, pushing InvoicedPeriod ahead of RenewalDate. Nexudus stops invoicing when InvoicedPeriod reaches the cancellation date |
| `--contract-term` | DateTime | Minimum contract length end date. Defines the earliest date at which the contract can be cancelled without penalty |
| `--price` | decimal | Fixed price override for this contract. If null, the contract uses the plan's default price (TariffPrice) |
| `--value` | decimal | Contract value used in reporting to compare against the actual invoiced price |
| `--desks` | list, repeat flag | List of desks linked to this record |
| `--added-desks` | list, repeat flag | The added desks value for this coworker contract |
| `--removed-desks` | list, repeat flag | The removed desks value for this coworker contract |
| `--variants` | list, repeat flag | List of variants linked to this record |
| `--added-variants` | list, repeat flag | The added variants value for this coworker contract |
| `--removed-variants` | list, repeat flag | The removed variants value for this coworker contract |
| `--quantity` | int | Number of units |
| `--purchase-order` | string | Purchase order |
| `--include-signup-fee` | bool | Whether to include the plan's signup fee when creating this contract |
| `--invoice-advanced-cycles` | bool | Whether to invoice multiple billing cycles in advance on the first invoice, as configured by Tariff.AdvanceInvoiceCycles |
| `--apply-pro-rating` | bool | Whether to pro-rate the first invoice based on the contract start date relative to the billing cycle |
| `--next-auto-invoice` | DateTime | Date of the next automatic invoice generation for this contract |
| `--price-plan-terms-accepted` | bool | Whether the customer has accepted the plan's terms and conditions |
| `--cancellation-date` | DateTime | Date on which the contract will be cancelled. Nexudus stops invoicing when InvoicedPeriod reaches this date |
| `--cancellation-limit-days` | int | Minimum number of days' notice required before cancellation takes effect |
| `--pro-rate-cancellation` | bool | Whether to pro-rate the final invoice when the contract is cancelled mid-cycle |
| `--cancel-team-contracts` | bool | Whether to cascade cancellation to contracts of team members under this customer |
| `--cancellation-reason` | enum | Reason for cancellation |
| `--cancellation-notes` | string | Free-text notes about the cancellation |
| `--delivery-preference-checks` | enum | Delivery handling preference for checks |
| `--delivery-preference-mail` | enum | Delivery handling preference for mail |
| `--delivery-preference-parcels` | enum | Delivery handling preference for parcels |
| `--delivery-preference-publicity` | enum | Delivery handling preference for publicity |
| `--delivery-instructions` | string | Free-text delivery instructions for this contract's mail handling |
| `--identity-checks-due-on` | DateTime | Date by which identity verification checks must be completed for this contract |
| `--address-checks-due-on` | DateTime | Date by which address verification checks must be completed for this contract |
| `--start-date-local` | DateTime | Date/time value for start date local |
| `--renewal-date-local` | DateTime | Date/time value for renewal date local |
| `--next-auto-invoice-local` | DateTime | Date/time value for next auto invoice local |
| `--price-plan-terms-accepted-on-local` | DateTime | Date/time value for price plan terms accepted on local |
| `--cancellation-date-local` | DateTime | Date/time value for cancellation date local |
| `--contract-term-local` | DateTime | Date/time value for contract term local |
| `--invoiced-period-local` | DateTime | Date/time value for invoiced period local |
| `--po-box-number` | string | PO box number |
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
