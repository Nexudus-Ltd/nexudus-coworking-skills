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
| `nexudus proposals create --issued-by-id <value> --responsible-id <value> --coworker-id <value> --reference <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create proposal |
| `nexudus proposals update <id> --name "New Name" --agent` | Update proposal |
| `nexudus proposals delete <id> --yes --agent` | Delete proposal (no prompt) |

#### Proposal list filter options

`--issued-by-id`, `--responsible-id`, `--coworker-id`, `--reference`, `--notes`, `--proposal-status`, `--document-to-send-id`, `--document-to-sign-id`, `--document-to-sign-html`, `--new-document-to-sign-binary-document-url`, `--clear-document-to-sign-binary-document-file`, `--document-to-send-html`, `--new-document-to-send-binary-document-url`, `--clear-document-to-send-binary-document-file`, `--new-proposal-file-url`, `--clear-proposal-file-file`, `--tariff-id`, `--price`, `--from-price` (range), `--to-price` (range), `--start-date`, `--from-start-date` (range), `--to-start-date` (range), `--cancellation-limit-days`, `--from-cancellation-limit-days` (range), `--to-cancellation-limit-days` (range), `--contract-term`, `--from-contract-term` (range), `--to-contract-term` (range), `--cancellation-date`, `--from-cancellation-date` (range), `--to-cancellation-date` (range), `--expiration-date`, `--from-expiration-date` (range), `--to-expiration-date` (range), `--billing-day`, `--from-billing-day` (range), `--to-billing-day` (range), `--quantity`, `--from-quantity` (range), `--to-quantity` (range), `--discount-code-id`, `--start-date-local`, `--from-start-date-local` (range), `--to-start-date-local` (range), `--sent-on-local`, `--from-sent-on-local` (range), `--to-sent-on-local` (range), `--do-not-issue-invoice`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### Proposal create options

`--issued-by-id` (required), `--responsible-id` (required), `--coworker-id` (required), `--reference` (required), `--notes`, `--proposal-status`, `--document-to-send-id`, `--document-to-sign-id`, `--document-to-sign-html`, `--new-document-to-sign-binary-document-url`, `--clear-document-to-sign-binary-document-file`, `--document-to-send-html`, `--new-document-to-send-binary-document-url`, `--clear-document-to-send-binary-document-file`, `--new-proposal-file-url`, `--clear-proposal-file-file`, `--tariff-id` (required), `--desks` (list, repeat flag), `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--variants` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--price`, `--start-date`, `--cancellation-limit-days`, `--contract-term`, `--cancellation-date`, `--expiration-date`, `--billing-day` (required), `--quantity` (required), `--discount-code-id`, `--start-date-local`, `--sent-on-local`, `--do-not-issue-invoice`

#### Proposal update options

`--issued-by-id`, `--responsible-id`, `--coworker-id`, `--reference`, `--notes`, `--proposal-status`, `--document-to-send-id`, `--document-to-sign-id`, `--document-to-sign-html`, `--new-document-to-sign-binary-document-url`, `--clear-document-to-sign-binary-document-file`, `--document-to-send-html`, `--new-document-to-send-binary-document-url`, `--clear-document-to-send-binary-document-file`, `--new-proposal-file-url`, `--clear-proposal-file-file`, `--added-desks` (list, repeat flag), `--removed-desks` (list, repeat flag), `--added-variants` (list, repeat flag), `--removed-variants` (list, repeat flag), `--cancellation-limit-days`, `--contract-term`, `--expiration-date`, `--start-date-local`, `--sent-on-local`

### Proposal (key fields)

`Id`, `ResponsibleFullName`, `CoworkerFullName`, `Reference`, `ProposalStatus`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`

#### Proposal enum values

| Option | Valid values |
| ------ | ------------ |
| `--proposal-status` | `1` Draft, `2` Sent, `3` Accepted, `4` Rejected |

<!-- END:GENERATED entity=Proposals -->
