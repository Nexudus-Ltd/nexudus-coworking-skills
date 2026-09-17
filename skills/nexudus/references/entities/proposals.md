# Proposals

<!-- BEGIN:GENERATED entity=Proposals -->

A Proposal is a priced offer of one or more contracts that a customer reviews and accepts online. Creating a proposal automatically creates one ProposalContract from the proposal's own plan, unit, price, and date fields; those fields are create-only here, so later changes must be made on that ProposalContract, and further contracts are added as additional ProposalContract records. Extra products and deposits are held as ProposalProduct records and scheduled price changes as ProposalSchedule records. Three attachments are optional: DocumentToSendId, a document template rendered for the customer in place of the standard price-schedule table; DocumentToSignId, a document template generated for e-signature on acceptance; and ProposalFile, a marketing file the customer can download. Sending the proposal stamps SentOn and moves the status to Sent; acceptance creates the real contracts, products, and discount on the customer and sets the status to Accepted, after which no field on the proposal can be changed.

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
| `--issued-by-id` | long | ID of the location that issued this proposal; it is supplied from the agent's current location context and its currency is the one all proposal amounts are expressed in. |
| `--issued-by-name` | string | Display value for IssuedBy.Name. |
| `--issued-by-currency-code` | string | Display value for IssuedBy.Currency.Code. |
| `--responsible-id` | long | ID of the staff user who owns this proposal; required, and their email address is notified when the customer completes an e-signed document. |
| `--responsible-full-name` | string | Display value for Responsible.FullName. |
| `--coworker-id` | long | ID of the customer the proposal is addressed to; required, and on acceptance the contracts, products, and discount of this proposal are created against this customer. |
| `--coworker-type` | string | Display value for Coworker.CoworkerType. |
| `--coworker-full-name` | string | Display value for Coworker.FullName. |
| `--coworker-company-name` | string | Display value for Coworker.CompanyName. |
| `--coworker-billing-name` | string | Display value for Coworker.BillingName. |
| `--reference` | string | Required human-readable reference shown to the customer and used to name the generated e-signature document; the admin UI seeds it as a random six-character code followed by the customer and plan names. |
| `--notes` | string | Free-text notes about this proposal; they are shown to the customer on the proposal page, so they are not internal-only. |
| `--proposal-status` | enum | Lifecycle state of the proposal: Draft, Sent (stamped when the proposal is emailed), Accepted (set only by the acceptance flow, after which no field on the proposal can be changed), or Rejected (set manually to withdraw the offer). |
| `--document-to-send-id` | long | Optional ID of the document template rendered for the customer in place of the standard price-schedule table; when empty, the standard layout is used. |
| `--document-to-sign-id` | long | Optional ID of the document template used to generate the document the customer is asked to e-sign when the proposal is accepted; when empty, no signature is requested. |
| `--document-to-sign-html` | string | Per-proposal HTML copy of the document to e-sign, produced from DocumentToSign and editable in the document editor; it is cleared automatically whenever DocumentToSign changes. |
| `--document-to-sign-binary-document-file-name` | string | Current file name of the document to sign binary document (read-only; upload via the corresponding URL field) |
| `--new-document-to-sign-binary-document-url` | string | URL of a new file to upload as the document to sign binary document |
| `--clear-document-to-sign-binary-document-file` | bool | Set to true to remove the current document to sign binary document file |
| `--document-to-send-html` | string | Per-proposal HTML copy of the document presented to the customer, produced from DocumentToSend and editable in the document editor; it is cleared automatically whenever DocumentToSend changes. |
| `--document-to-send-binary-document-file-name` | string | Current file name of the document to send binary document (read-only; upload via the corresponding URL field) |
| `--new-document-to-send-binary-document-url` | string | URL of a new file to upload as the document to send binary document |
| `--clear-document-to-send-binary-document-file` | bool | Set to true to remove the current document to send binary document file |
| `--proposal-file-file-name` | string | Current file name of the proposal file (read-only; upload via the corresponding URL field) |
| `--new-proposal-file-url` | string | URL of a new file to upload as the proposal file |
| `--clear-proposal-file-file` | bool | Set to true to remove the current proposal file file |
| `--tariff-id` | long | ID of the plan being quoted; required, and it is copied into the ProposalContract created with the proposal, so a different plan must be set on that ProposalContract instead. |
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
| `--price` | decimal | Optional per-unit price override for the quoted contract, in the issuing location's currency; when empty the plan's own price is used. It is copied into the ProposalContract created with the proposal, so later price changes belong on that ProposalContract. |
| `--from-price` | range | |
| `--to-price` | range | |
| `--start-date` | DateTime | Date the quoted contract starts; when empty, acceptance starts it the day after the proposal is accepted. It is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--from-start-date` | range | |
| `--to-start-date` | range | |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice, in days before the next billing day, for the quoted contract; when empty the plan's own notice period applies. It seeds the ProposalContract created with the proposal and cannot be changed here afterwards, so later changes belong on that ProposalContract. |
| `--from-cancellation-limit-days` | range | |
| `--to-cancellation-limit-days` | range | |
| `--contract-term` | DateTime | End date of the minimum term for the quoted contract; when empty, the contract derives its own term from the plan's default term and start date. It seeds the ProposalContract created with the proposal and cannot be changed here afterwards, so later changes belong on that ProposalContract. |
| `--from-contract-term` | range | |
| `--to-contract-term` | range | |
| `--cancellation-date` | DateTime | Optional date on which the quoted contract ends; leave empty for an open-ended contract. It is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--from-cancellation-date` | range | |
| `--to-cancellation-date` | range | |
| `--expiration-date` | DateTime | Last date the customer may still accept this proposal; acceptance and e-signing are refused once the current UTC time passes this date plus one day, and when empty the proposal expires 30 days after it was created. It stays editable after creation. |
| `--from-expiration-date` | range | |
| `--to-expiration-date` | range | |
| `--billing-day` | int | Day of the month, from 1 to 28, on which the quoted contract is invoiced; it is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--from-billing-day` | range | |
| `--to-billing-day` | range | |
| `--quantity` | int | Number of plan units quoted, at least 1; it multiplies the unit price. It is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--from-quantity` | range | |
| `--to-quantity` | range | |
| `--discount-code-id` | long | Optional ID of a discount code quoted with this proposal; on acceptance it is both copied into the contract and added to the customer's account. |
| `--sent-on` | DateTime | UTC date and time the proposal was last emailed to the customer; the send action stamps it and no other flow sets it. |
| `--from-sent-on` | range | |
| `--to-sent-on` | range | |
| `--customer-last-opened-date` | DateTime | UTC date and time the customer last opened the public proposal page; it is stamped automatically on each view and stays empty while the customer has never opened it. |
| `--from-customer-last-opened-date` | range | |
| `--to-customer-last-opened-date` | range | |
| `--do-not-issue-invoice` | bool | Whether the contracts created on acceptance are left paused with no renewal date, so no invoice is issued automatically; the location's Billing.DoNotIssueInvoice setting supplies the default. It is read from the proposal at the moment of acceptance, never copied into the ProposalContract, so it can still be changed while the proposal is not accepted. |
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
| `--issued-by-id` | long, required | ID of the location that issued this proposal; it is supplied from the agent's current location context and its currency is the one all proposal amounts are expressed in. |
| `--responsible-id` | long, required | ID of the staff user who owns this proposal; required, and their email address is notified when the customer completes an e-signed document. |
| `--coworker-id` | long, required | ID of the customer the proposal is addressed to; required, and on acceptance the contracts, products, and discount of this proposal are created against this customer. |
| `--reference` | string, required | Required human-readable reference shown to the customer and used to name the generated e-signature document; the admin UI seeds it as a random six-character code followed by the customer and plan names. |
| `--notes` | string | Free-text notes about this proposal; they are shown to the customer on the proposal page, so they are not internal-only. |
| `--proposal-status` | enum, required | Lifecycle state of the proposal: Draft, Sent (stamped when the proposal is emailed), Accepted (set only by the acceptance flow, after which no field on the proposal can be changed), or Rejected (set manually to withdraw the offer). |
| `--document-to-send-id` | long | Optional ID of the document template rendered for the customer in place of the standard price-schedule table; when empty, the standard layout is used. |
| `--document-to-sign-id` | long | Optional ID of the document template used to generate the document the customer is asked to e-sign when the proposal is accepted; when empty, no signature is requested. |
| `--document-to-sign-html` | string | Per-proposal HTML copy of the document to e-sign, produced from DocumentToSign and editable in the document editor; it is cleared automatically whenever DocumentToSign changes. |
| `--new-document-to-sign-binary-document-url` | string | URL of a new file to upload as the document to sign binary document |
| `--clear-document-to-sign-binary-document-file` | bool | Set to true to remove the current document to sign binary document file |
| `--document-to-send-html` | string | Per-proposal HTML copy of the document presented to the customer, produced from DocumentToSend and editable in the document editor; it is cleared automatically whenever DocumentToSend changes. |
| `--new-document-to-send-binary-document-url` | string | URL of a new file to upload as the document to send binary document |
| `--clear-document-to-send-binary-document-file` | bool | Set to true to remove the current document to send binary document file |
| `--new-proposal-file-url` | string | URL of a new file to upload as the proposal file |
| `--clear-proposal-file-file` | bool | Set to true to remove the current proposal file file |
| `--tariff-id` | long, required | ID of the plan being quoted; required, and it is copied into the ProposalContract created with the proposal, so a different plan must be set on that ProposalContract instead. |
| `--desks` | list, repeat flag | List of IDs of the floor-plan units quoted in this proposal; each unit must belong to a location the user can access, an empty list means no unit is attached, and the list is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--added-desks` | list, repeat flag | IDs added to the Desks relationship. |
| `--removed-desks` | list, repeat flag | IDs removed from the Desks relationship. |
| `--variants` | list, repeat flag | List of IDs of the floor-plan unit packages quoted in this proposal; each package must belong to one of the units listed in Desks and to a location the user can access, an empty list means none, and the list is copied into the ProposalContract created with the proposal. |
| `--added-variants` | list, repeat flag | IDs added to the Variants relationship. |
| `--removed-variants` | list, repeat flag | IDs removed from the Variants relationship. |
| `--price` | decimal | Optional per-unit price override for the quoted contract, in the issuing location's currency; when empty the plan's own price is used. It is copied into the ProposalContract created with the proposal, so later price changes belong on that ProposalContract. |
| `--start-date` | DateTime | Date the quoted contract starts; when empty, acceptance starts it the day after the proposal is accepted. It is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--cancellation-limit-days` | int | Optional minimum cancellation notice, in days before the next billing day, for the quoted contract; when empty the plan's own notice period applies. It seeds the ProposalContract created with the proposal and cannot be changed here afterwards, so later changes belong on that ProposalContract. |
| `--contract-term` | DateTime | End date of the minimum term for the quoted contract; when empty, the contract derives its own term from the plan's default term and start date. It seeds the ProposalContract created with the proposal and cannot be changed here afterwards, so later changes belong on that ProposalContract. |
| `--cancellation-date` | DateTime | Optional date on which the quoted contract ends; leave empty for an open-ended contract. It is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--expiration-date` | DateTime | Last date the customer may still accept this proposal; acceptance and e-signing are refused once the current UTC time passes this date plus one day, and when empty the proposal expires 30 days after it was created. It stays editable after creation. |
| `--billing-day` | int, required | Day of the month, from 1 to 28, on which the quoted contract is invoiced; it is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--quantity` | int, required | Number of plan units quoted, at least 1; it multiplies the unit price. It is copied into the ProposalContract created with the proposal, so later changes belong on that ProposalContract. |
| `--discount-code-id` | long | Optional ID of a discount code quoted with this proposal; on acceptance it is both copied into the contract and added to the customer's account. |
| `--do-not-issue-invoice` | bool | Whether the contracts created on acceptance are left paused with no renewal date, so no invoice is issued automatically; the location's Billing.DoNotIssueInvoice setting supplies the default. It is read from the proposal at the moment of acceptance, never copied into the ProposalContract, so it can still be changed while the proposal is not accepted. |

#### Proposal update options

| Option | Type | Description |
| --- | --- | --- |
| `--issued-by-id` | long | ID of the location that issued this proposal; it is supplied from the agent's current location context and its currency is the one all proposal amounts are expressed in. |
| `--responsible-id` | long | ID of the staff user who owns this proposal; required, and their email address is notified when the customer completes an e-signed document. |
| `--coworker-id` | long | ID of the customer the proposal is addressed to; required, and on acceptance the contracts, products, and discount of this proposal are created against this customer. |
| `--reference` | string | Required human-readable reference shown to the customer and used to name the generated e-signature document; the admin UI seeds it as a random six-character code followed by the customer and plan names. |
| `--notes` | string | Free-text notes about this proposal; they are shown to the customer on the proposal page, so they are not internal-only. |
| `--proposal-status` | enum | Lifecycle state of the proposal: Draft, Sent (stamped when the proposal is emailed), Accepted (set only by the acceptance flow, after which no field on the proposal can be changed), or Rejected (set manually to withdraw the offer). |
| `--document-to-send-id` | long | Optional ID of the document template rendered for the customer in place of the standard price-schedule table; when empty, the standard layout is used. |
| `--document-to-sign-id` | long | Optional ID of the document template used to generate the document the customer is asked to e-sign when the proposal is accepted; when empty, no signature is requested. |
| `--document-to-sign-html` | string | Per-proposal HTML copy of the document to e-sign, produced from DocumentToSign and editable in the document editor; it is cleared automatically whenever DocumentToSign changes. |
| `--new-document-to-sign-binary-document-url` | string | URL of a new file to upload as the document to sign binary document |
| `--clear-document-to-sign-binary-document-file` | bool | Set to true to remove the current document to sign binary document file |
| `--document-to-send-html` | string | Per-proposal HTML copy of the document presented to the customer, produced from DocumentToSend and editable in the document editor; it is cleared automatically whenever DocumentToSend changes. |
| `--new-document-to-send-binary-document-url` | string | URL of a new file to upload as the document to send binary document |
| `--clear-document-to-send-binary-document-file` | bool | Set to true to remove the current document to send binary document file |
| `--new-proposal-file-url` | string | URL of a new file to upload as the proposal file |
| `--clear-proposal-file-file` | bool | Set to true to remove the current proposal file file |
| `--added-desks` | list, repeat flag | IDs added to the Desks relationship. |
| `--removed-desks` | list, repeat flag | IDs removed from the Desks relationship. |
| `--added-variants` | list, repeat flag | IDs added to the Variants relationship. |
| `--removed-variants` | list, repeat flag | IDs removed from the Variants relationship. |
| `--expiration-date` | DateTime | Last date the customer may still accept this proposal; acceptance and e-signing are refused once the current UTC time passes this date plus one day, and when empty the proposal expires 30 days after it was created. It stays editable after creation. |
| `--do-not-issue-invoice` | bool | Whether the contracts created on acceptance are left paused with no renewal date, so no invoice is issued automatically; the location's Billing.DoNotIssueInvoice setting supplies the default. It is read from the proposal at the moment of acceptance, never copied into the ProposalContract, so it can still be changed while the proposal is not accepted. |

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
