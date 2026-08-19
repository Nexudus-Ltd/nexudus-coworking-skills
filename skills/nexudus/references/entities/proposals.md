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
| `nexudus proposals list --responsible-full-name <value> --coworker-full-name <value> --agent` | Filter proposals by properties |
| `nexudus proposals list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus proposals list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus proposals get <id> --agent` | Get single proposal |
| `nexudus proposals create --issued-by-id <value> --responsible-id <value> --coworker-id <value> --reference <value> --proposal-status <value> --tariff-id <value> --billing-day <value> --quantity <value> --agent` | Create proposal |
| `nexudus proposals update <id> --name "New Name" --agent` | Update proposal |
| `nexudus proposals delete <id> --yes --agent` | Delete proposal (no prompt) |

#### Proposal list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long | ID of the issued by linked to this record |
| `--issued-by-name` | string | Issuing business name |
| `--issued-by-currency-code` | string | Issuing business currency code |
| `--responsible-id` | long | ID of the responsible linked to this record |
| `--responsible-full-name` | string | Responsible person full name |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--coworker-type` | string | Coworker type |
| `--coworker-full-name` | string | Coworker full name |
| `--coworker-company-name` | string | Coworker company name |
| `--coworker-billing-name` | string | Coworker billing name |
| `--reference` | string | Proposal reference |
| `--notes` | string | Optional notes or comments about this proposal |
| `--proposal-status` | enum | Proposal status |
| `--document-to-send-id` | long | ID of the document to send linked to this record |
| `--document-to-sign-id` | long | ID of the document to sign linked to this record |
| `--document-to-sign-html` | string | The document to sign html value for this proposal |
| `--document-to-sign-binary-document-file-name` | string | Current file name of the document to sign binary document (read-only; upload via the corresponding URL field) |
| `--new-document-to-sign-binary-document-url` | string | URL of a new file to upload as the document to sign binary document |
| `--clear-document-to-sign-binary-document-file` | bool | Set to true to remove the current document to sign binary document file |
| `--document-to-send-html` | string | The document to send html value for this proposal |
| `--document-to-send-binary-document-file-name` | string | Current file name of the document to send binary document (read-only; upload via the corresponding URL field) |
| `--new-document-to-send-binary-document-url` | string | URL of a new file to upload as the document to send binary document |
| `--clear-document-to-send-binary-document-file` | bool | Set to true to remove the current document to send binary document file |
| `--proposal-file-file-name` | string | Current file name of the proposal file (read-only; upload via the corresponding URL field) |
| `--new-proposal-file-url` | string | URL of a new file to upload as the proposal file |
| `--clear-proposal-file-file` | bool | Set to true to remove the current proposal file file |
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
| `--discount-code-id` | long | ID of the discount code linked to this record |
| `--start-date-local` | DateTime | Date/time value for start date local |
| `--from-start-date-local` | range | |
| `--to-start-date-local` | range | |
| `--sent-on` | DateTime | Date the proposal was sent |
| `--from-sent-on` | range | |
| `--to-sent-on` | range | |
| `--sent-on-local` | DateTime | Date/time value for sent on local |
| `--from-sent-on-local` | range | |
| `--to-sent-on-local` | range | |
| `--customer-last-opened-date` | DateTime | Date the customer last opened the proposal |
| `--from-customer-last-opened-date` | range | |
| `--to-customer-last-opened-date` | range | |
| `--do-not-issue-invoice` | bool | If true, the first invoice is not issued automatically when the proposal is accepted |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### Proposal sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### Proposal create options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long, required | ID of the issued by linked to this record |
| `--responsible-id` | long, required | ID of the responsible linked to this record |
| `--coworker-id` | long, required | ID of the coworker linked to this record |
| `--reference` | string, required | Proposal reference |
| `--notes` | string | Optional notes or comments about this proposal |
| `--proposal-status` | enum, required | Proposal status |
| `--document-to-send-id` | long | ID of the document to send linked to this record |
| `--document-to-sign-id` | long | ID of the document to sign linked to this record |
| `--document-to-sign-html` | string | The document to sign html value for this proposal |
| `--new-document-to-sign-binary-document-url` | string | URL of a new file to upload as the document to sign binary document |
| `--clear-document-to-sign-binary-document-file` | bool | Set to true to remove the current document to sign binary document file |
| `--document-to-send-html` | string | The document to send html value for this proposal |
| `--new-document-to-send-binary-document-url` | string | URL of a new file to upload as the document to send binary document |
| `--clear-document-to-send-binary-document-file` | bool | Set to true to remove the current document to send binary document file |
| `--new-proposal-file-url` | string | URL of a new file to upload as the proposal file |
| `--clear-proposal-file-file` | bool | Set to true to remove the current proposal file file |
| `--tariff-id` | long, required | ID of the tariff linked to this record |
| `--desks` | list, repeat flag | List of desks linked to this record |
| `--added-desks` | list, repeat flag | The added desks value for this proposal |
| `--removed-desks` | list, repeat flag | The removed desks value for this proposal |
| `--variants` | list, repeat flag | List of variants linked to this record |
| `--added-variants` | list, repeat flag | The added variants value for this proposal |
| `--removed-variants` | list, repeat flag | The removed variants value for this proposal |
| `--price` | decimal | Price override for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--start-date` | DateTime | Start date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--cancellation-limit-days` | int | Cancellation limit in days for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--contract-term` | DateTime | Contract term end date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--cancellation-date` | DateTime | Cancellation date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--expiration-date` | DateTime | Proposal expiration date. Becomes read-only after creation; edit via ProposalContract |
| `--billing-day` | int, required | Billing day of month for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--quantity` | int, required | Quantity for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--discount-code-id` | long | ID of the discount code linked to this record |
| `--start-date-local` | DateTime | Date/time value for start date local |
| `--sent-on-local` | DateTime | Date/time value for sent on local |
| `--do-not-issue-invoice` | bool | If true, the first invoice is not issued automatically when the proposal is accepted |

#### Proposal update options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long | ID of the issued by linked to this record |
| `--responsible-id` | long | ID of the responsible linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--reference` | string | Proposal reference |
| `--notes` | string | Optional notes or comments about this proposal |
| `--proposal-status` | enum | Proposal status |
| `--document-to-send-id` | long | ID of the document to send linked to this record |
| `--document-to-sign-id` | long | ID of the document to sign linked to this record |
| `--document-to-sign-html` | string | The document to sign html value for this proposal |
| `--new-document-to-sign-binary-document-url` | string | URL of a new file to upload as the document to sign binary document |
| `--clear-document-to-sign-binary-document-file` | bool | Set to true to remove the current document to sign binary document file |
| `--document-to-send-html` | string | The document to send html value for this proposal |
| `--new-document-to-send-binary-document-url` | string | URL of a new file to upload as the document to send binary document |
| `--clear-document-to-send-binary-document-file` | bool | Set to true to remove the current document to send binary document file |
| `--new-proposal-file-url` | string | URL of a new file to upload as the proposal file |
| `--clear-proposal-file-file` | bool | Set to true to remove the current proposal file file |
| `--added-desks` | list, repeat flag | The added desks value for this proposal |
| `--removed-desks` | list, repeat flag | The removed desks value for this proposal |
| `--added-variants` | list, repeat flag | The added variants value for this proposal |
| `--removed-variants` | list, repeat flag | The removed variants value for this proposal |
| `--cancellation-limit-days` | int | Cancellation limit in days for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--contract-term` | DateTime | Contract term end date for the initial contract. Becomes read-only after creation; edit via ProposalContract |
| `--expiration-date` | DateTime | Proposal expiration date. Becomes read-only after creation; edit via ProposalContract |
| `--start-date-local` | DateTime | Date/time value for start date local |
| `--sent-on-local` | DateTime | Date/time value for sent on local |

#### Proposal PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--responsible-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus proposals update <id> --responsible-full-name "«PII:NAME:a3f2b1c9»" --agent`

### Proposal (key fields)

`Id`, `ResponsibleFullName`, `CoworkerFullName`, `Reference`, `ProposalStatus`

**List properties (only returned by `get`, not by `list`):** `Desks`, `AddedDesks`, `RemovedDesks`, `Variants`, `AddedVariants`, `RemovedVariants`

#### Proposal enum values

| Option | Valid values |
| ------ | ------------ |
| `--proposal-status` | `1` Draft, `2` Sent, `3` Accepted, `4` Rejected |

<!-- END:GENERATED entity=Proposals -->
