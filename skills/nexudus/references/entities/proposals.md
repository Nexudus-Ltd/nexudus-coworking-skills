# Proposals

<!-- BEGIN:GENERATED entity=Proposals -->

A **Proposal** bundles one or more contracts (`ProposalContract` records) that are presented to a customer for review and acceptance. Each `ProposalContract` carries the same properties as a `CoworkerContract` and becomes one when the proposal is accepted.

When a Proposal is created, a `ProposalContract` is automatically created and associated with it. From that point on, the contract-related fields on the Proposal (`TariffId`, `Desks`, `Variants`, `Price`, `StartDate`, `CancellationLimitDays`, `ContractTerm`, `CancellationDate`, `ExpirationDate`, `BillingDay`, `Quantity`) become read-only — they are all `createOnly`. Subsequent edits to those values must be made via the associated `ProposalContract`. Additional `ProposalContract` records can also be added.

Proposals support three optional attachments:

- **DocumentToSendId** — a `DocumentTemplate` entity presented to the customer instead of the standard price-schedule table before the proposal is accepted.
- **DocumentToSignId** — a `DocumentTemplate` entity used to generate a document for e-signature.
- **ProposalFile** — a file shown as a downloadable link before the proposal is accepted.

Set `DoNotIssueInvoice` to control whether the first invoice is issued automatically when the proposal is accepted.

Proposals support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus proposals list --agent` | List all proposals |
| `nexudus proposals list --id <id> --agent` | Filter by single ID |
| `nexudus proposals list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus proposals list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus proposals list --reference <value> --proposal-status <value> --agent` | Filter proposals by properties |
| `nexudus proposals list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposals get <id> --agent` | Get single proposal |
| `nexudus proposals create --issued-by-id <value> --responsible-id <value> --coworker-id <value> --reference <value> --proposal-status <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create proposal |
| `nexudus proposals update <id> --name "New Name" --agent` | Update proposal |
| `nexudus proposals delete <id> --yes --agent` | Delete proposal (no prompt) |

#### Proposal list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long |  |
| `--responsible-id` | long |  |
| `--coworker-id` | long |  |
| `--reference` | string | Proposal reference |
| `--notes` | string | Notes |
| `--proposal-status` | enum | Proposal status |
| `--document-to-send-id` | long |  |
| `--document-to-sign-id` | long |  |
| `--document-to-sign-html` | string |  |
| `--new-document-to-sign-binary-document-url` | string |  |
| `--clear-document-to-sign-binary-document-file` | bool |  |
| `--document-to-send-html` | string |  |
| `--new-document-to-send-binary-document-url` | string |  |
| `--clear-document-to-send-binary-document-file` | bool |  |
| `--new-proposal-file-url` | string |  |
| `--clear-proposal-file-file` | bool |  |
| `--tariff-id` | long |  |
| `--price` | decimal | Price override for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--from-price` | range | |
| `--to-price` | range | |
| `--start-date` | DateTime | Start date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--cancellation-limit-days` | int | Cancellation limit in days for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--from-cancellation-limit-days` | range | |
| `--to-cancellation-limit-days` | range | |
| `--contract-term` | DateTime | Contract term end date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--from-contract-term` | range | |
| `--to-contract-term` | range | |
| `--cancellation-date` | DateTime | Cancellation date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--from-cancellation-date` | range | |
| `--to-cancellation-date` | range | |
| `--expiration-date` | DateTime | Proposal expiration date. Becomes read-only after creation; edit via ProposalContract |
| `--from-expiration-date` | range | |
| `--to-expiration-date` | range | |
| `--billing-day` | int | Billing day of month for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--from-billing-day` | range | |
| `--to-billing-day` | range | |
| `--quantity` | int | Quantity for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--discount-code-id` | long |  |
| `--start-date-local` | DateTime |  |
| `--from-start-date-local` | range | |
| `--to-start-date-local` | range | |
| `--sent-on-local` | DateTime |  |
| `--from-sent-on-local` | range | |
| `--to-sent-on-local` | range | |
| `--do-not-issue-invoice` | bool | If true, the first invoice is not issued automatically when the proposal is accepted |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Proposal create options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long, required |  |
| `--responsible-id` | long, required |  |
| `--coworker-id` | long, required |  |
| `--reference` | string, required | Proposal reference |
| `--notes` | string | Notes |
| `--proposal-status` | enum, required | Proposal status |
| `--document-to-send-id` | long |  |
| `--document-to-sign-id` | long |  |
| `--document-to-sign-html` | string |  |
| `--new-document-to-sign-binary-document-url` | string |  |
| `--clear-document-to-sign-binary-document-file` | bool |  |
| `--document-to-send-html` | string |  |
| `--new-document-to-send-binary-document-url` | string |  |
| `--clear-document-to-send-binary-document-file` | bool |  |
| `--new-proposal-file-url` | string |  |
| `--clear-proposal-file-file` | bool |  |
| `--tariff-id` | long, required |  |
| `--desks` | list, repeat flag |  |
| `--added-desks` | list, repeat flag |  |
| `--removed-desks` | list, repeat flag |  |
| `--variants` | list, repeat flag |  |
| `--added-variants` | list, repeat flag |  |
| `--removed-variants` | list, repeat flag |  |
| `--price` | decimal | Price override for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--start-date` | DateTime | Start date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--cancellation-limit-days` | int | Cancellation limit in days for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--contract-term` | DateTime | Contract term end date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--cancellation-date` | DateTime | Cancellation date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--expiration-date` | DateTime | Proposal expiration date. Becomes read-only after creation; edit via ProposalContract |
| `--billing-day` | int, required | Billing day of month for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--quantity` | int, required | Quantity for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--discount-code-id` | long |  |
| `--start-date-local` | DateTime |  |
| `--sent-on-local` | DateTime |  |
| `--do-not-issue-invoice` | bool | If true, the first invoice is not issued automatically when the proposal is accepted |

#### Proposal update options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long |  |
| `--responsible-id` | long |  |
| `--coworker-id` | long |  |
| `--reference` | string | Proposal reference |
| `--notes` | string | Notes |
| `--proposal-status` | enum | Proposal status |
| `--document-to-send-id` | long |  |
| `--document-to-sign-id` | long |  |
| `--document-to-sign-html` | string |  |
| `--new-document-to-sign-binary-document-url` | string |  |
| `--clear-document-to-sign-binary-document-file` | bool |  |
| `--document-to-send-html` | string |  |
| `--new-document-to-send-binary-document-url` | string |  |
| `--clear-document-to-send-binary-document-file` | bool |  |
| `--new-proposal-file-url` | string |  |
| `--clear-proposal-file-file` | bool |  |
| `--added-desks` | list, repeat flag |  |
| `--removed-desks` | list, repeat flag |  |
| `--added-variants` | list, repeat flag |  |
| `--removed-variants` | list, repeat flag |  |
| `--cancellation-limit-days` | int | Cancellation limit in days for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--contract-term` | DateTime | Contract term end date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--expiration-date` | DateTime | Proposal expiration date. Becomes read-only after creation; edit via ProposalContract |
| `--start-date-local` | DateTime |  |
| `--sent-on-local` | DateTime |  |

### Proposal (key fields)

`Id`, `ResponsibleFullName`, `CoworkerFullName`, `Reference`, `ProposalStatus`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`

#### Proposal enum values

| Option | Valid values |
| ------ | ------------ |
| `--proposal-status` | `1` Draft, `2` Sent, `3` Accepted, `4` Rejected |

<!-- END:GENERATED entity=Proposals -->
