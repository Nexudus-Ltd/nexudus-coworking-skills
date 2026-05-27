# ContractContacts

<!-- BEGIN:GENERATED entity=ContractContacts -->

A **ContractContact** is a key contact entry on a virtual office contract (`CoworkerContract`). Contacts can be directors, company aliases, or nominated recipients, and are used to identify, validate, and handle mail and deliveries addressed to anyone connected to a virtual office contract.

Each entry can be linked to an existing coworker via `--coworker-id`, in which case the coworker's name and email are resolved automatically. Alternatively, provide `--full-name` and `--email` directly for contacts who do not have a coworker record.

Use `--contract-contact-type` to classify the contact:

| Type                | Description                                                                 |
| ------------------- | --------------------------------------------------------------------------- |
| `Director`          | A director of the company registered under the virtual office contract      |
| `CompanyAlias`      | A trading name or alias used by the company                                 |
| `NominatedRecipient`| A person authorised to receive mail and deliveries on behalf of the company |

ContractContacts support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractcontacts list --agent` | List all contractcontacts |
| `nexudus contractcontacts list --id <id> --agent` | Filter by single ID |
| `nexudus contractcontacts list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractcontacts list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractcontacts list --email <value> --full-name <value> --agent` | Filter contractcontacts by properties |
| `nexudus contractcontacts list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractcontacts get <id> --agent` | Get single contractcontact |
| `nexudus contractcontacts create --coworker-contract-id <value> --full-name <value> --contract-contact-type <value> --aml-check-status <value> --agent` | Create contractcontact |
| `nexudus contractcontacts update <id> --name "New Name" --agent` | Update contractcontact |
| `nexudus contractcontacts delete <id> --yes --agent` | Delete contractcontact (no prompt) |

#### ContractContact list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the coworker contract linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--email` | string | Email address of the contact. Used when the contact is not linked to a coworker record |
| `--full-name` | string | Full name of the contact. Used when the contact is not linked to a coworker record |
| `--date-of-birth` | DateTime | Date of birth. Used for identity verification purposes |
| `--from-date-of-birth` | range | |
| `--to-date-of-birth` | range | |
| `--address` | string | Street address |
| `--post-code` | string | Post code |
| `--city-name` | string | City name |
| `--state` | string | State or province |
| `--country-id` | long | ID of the country linked to this record |
| `--phone-number` | string | Phone number |
| `--notes` | string | Optional notes or comments about this contract contact |
| `--contract-contact-type` | enum | Role of this contact: Director (a company director), CompanyAlias (a trading name), or NominatedRecipient (authorised to receive mail on behalf of the company) |
| `--aml-check-status` | enum | The AML check status for this contact |
| `--aml-check-date` | DateTime | The date when the AML check was performed |
| `--from-aml-check-date` | range | |
| `--to-aml-check-date` | range | |
| `--aml-open-sanctions-score` | decimal | The score from the open sanctions check |
| `--from-aml-open-sanctions-score` | range | |
| `--to-aml-open-sanctions-score` | range | |
| `--aml-open-sanctions-response` | string | The response from the open sanctions check as JSON string |
| `--aml-pappers-response` | string | The response from the Pappers AML check as TEXT string |
| `--aml-pappers-status` | string | The status from the Pappers AML check |
| `--aml-notes` | string | Notes related to the AML check. Customers cannot see this field, it's for internal use only |
| `--aml-cleared-by` | string | The user who cleared the AML check |
| `--aml-cleared-on` | DateTime | The date when the AML check was cleared |
| `--from-aml-cleared-on` | range | |
| `--to-aml-cleared-on` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractContact create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long, required | ID of the coworker contract linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--email` | string | Email address of the contact. Used when the contact is not linked to a coworker record |
| `--full-name` | string, required | Full name of the contact. Used when the contact is not linked to a coworker record |
| `--date-of-birth` | DateTime | Date of birth. Used for identity verification purposes |
| `--address` | string | Street address |
| `--post-code` | string | Post code |
| `--city-name` | string | City name |
| `--state` | string | State or province |
| `--country-id` | long | ID of the country linked to this record |
| `--phone-number` | string | Phone number |
| `--notes` | string | Optional notes or comments about this contract contact |
| `--contract-contact-type` | enum, required | Role of this contact: Director (a company director), CompanyAlias (a trading name), or NominatedRecipient (authorised to receive mail on behalf of the company) |
| `--aml-check-status` | enum, required | The AML check status for this contact |
| `--aml-check-date` | DateTime | The date when the AML check was performed |
| `--aml-open-sanctions-score` | decimal | The score from the open sanctions check |
| `--aml-open-sanctions-response` | string | The response from the open sanctions check as JSON string |
| `--aml-pappers-response` | string | The response from the Pappers AML check as TEXT string |
| `--aml-pappers-status` | string | The status from the Pappers AML check |
| `--aml-notes` | string | Notes related to the AML check. Customers cannot see this field, it's for internal use only |
| `--aml-cleared-by` | string | The user who cleared the AML check |
| `--aml-cleared-on` | DateTime | The date when the AML check was cleared |

#### ContractContact update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the coworker contract linked to this record |
| `--coworker-id` | long | ID of the coworker linked to this record |
| `--email` | string | Email address of the contact. Used when the contact is not linked to a coworker record |
| `--full-name` | string | Full name of the contact. Used when the contact is not linked to a coworker record |
| `--date-of-birth` | DateTime | Date of birth. Used for identity verification purposes |
| `--address` | string | Street address |
| `--post-code` | string | Post code |
| `--city-name` | string | City name |
| `--state` | string | State or province |
| `--country-id` | long | ID of the country linked to this record |
| `--phone-number` | string | Phone number |
| `--notes` | string | Optional notes or comments about this contract contact |
| `--contract-contact-type` | enum | Role of this contact: Director (a company director), CompanyAlias (a trading name), or NominatedRecipient (authorised to receive mail on behalf of the company) |
| `--aml-check-status` | enum | The AML check status for this contact |
| `--aml-check-date` | DateTime | The date when the AML check was performed |
| `--aml-open-sanctions-score` | decimal | The score from the open sanctions check |
| `--aml-open-sanctions-response` | string | The response from the open sanctions check as JSON string |
| `--aml-pappers-response` | string | The response from the Pappers AML check as TEXT string |
| `--aml-pappers-status` | string | The status from the Pappers AML check |
| `--aml-notes` | string | Notes related to the AML check. Customers cannot see this field, it's for internal use only |
| `--aml-cleared-by` | string | The user who cleared the AML check |
| `--aml-cleared-on` | DateTime | The date when the AML check was cleared |

#### ContractContact PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-company-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--email` | `EMAIL` | `«PII:EMAIL:a3f2b1c9»` |
| `--full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--date-of-birth` | `DOB` | `«PII:DOB:a3f2b1c9»` |
| `--address` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--post-code` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--city-name` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--state` | `ADDRESS` | `«PII:ADDRESS:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus contractcontacts update <id> --coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### ContractContact (key fields)

`Id`, `CoworkerFullName`, `Email`, `FullName`, `ContractContactType`

#### ContractContact enum values

| Option | Valid values |
| ------ | ------------ |
| `--contract-contact-type` | `0` None, `1` Director, `2` CompanyAlias, `3` NominatedRecipient |
| `--aml-check-status` | `0` NotStarted, `1` Pending, `2` Clear, `3` PotentialMatch, `4` ConfirmedMatch, `5` Error, `6` ManuallyCleared |

<!-- END:GENERATED entity=ContractContacts -->
