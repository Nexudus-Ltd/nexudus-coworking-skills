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
| `nexudus contractcontacts create --coworker-contract-id <value> --full-name <value> --contract-contact-type <value> --agent` | Create contractcontact |
| `nexudus contractcontacts update <id> --name "New Name" --agent` | Update contractcontact |
| `nexudus contractcontacts delete <id> --yes --agent` | Delete contractcontact (no prompt) |

#### ContractContact list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long |  |
| `--coworker-id` | long |  |
| `--email` | string | Email address of the contact. Used when the contact is not linked to a coworker record |
| `--full-name` | string | Full name of the contact. Used when the contact is not linked to a coworker record |
| `--date-of-birth` | DateTime | Date of birth. Used for identity verification purposes |
| `--from-date-of-birth` | range | |
| `--to-date-of-birth` | range | |
| `--address` | string | Address |
| `--post-code` | string | Post code |
| `--city-name` | string | City name |
| `--state` | string | State |
| `--country-id` | long |  |
| `--phone-number` | string | Phone number |
| `--notes` | string | Notes |
| `--contract-contact-type` | enum | Role of this contact: Director (a company director), CompanyAlias (a trading name), or NominatedRecipient (authorised to receive mail on behalf of the company) |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractContact create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long, required |  |
| `--coworker-id` | long |  |
| `--email` | string | Email address of the contact. Used when the contact is not linked to a coworker record |
| `--full-name` | string, required | Full name of the contact. Used when the contact is not linked to a coworker record |
| `--date-of-birth` | DateTime | Date of birth. Used for identity verification purposes |
| `--address` | string | Address |
| `--post-code` | string | Post code |
| `--city-name` | string | City name |
| `--state` | string | State |
| `--country-id` | long |  |
| `--phone-number` | string | Phone number |
| `--notes` | string | Notes |
| `--contract-contact-type` | enum, required | Role of this contact: Director (a company director), CompanyAlias (a trading name), or NominatedRecipient (authorised to receive mail on behalf of the company) |

#### ContractContact update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long |  |
| `--coworker-id` | long |  |
| `--email` | string | Email address of the contact. Used when the contact is not linked to a coworker record |
| `--full-name` | string | Full name of the contact. Used when the contact is not linked to a coworker record |
| `--date-of-birth` | DateTime | Date of birth. Used for identity verification purposes |
| `--address` | string | Address |
| `--post-code` | string | Post code |
| `--city-name` | string | City name |
| `--state` | string | State |
| `--country-id` | long |  |
| `--phone-number` | string | Phone number |
| `--notes` | string | Notes |
| `--contract-contact-type` | enum | Role of this contact: Director (a company director), CompanyAlias (a trading name), or NominatedRecipient (authorised to receive mail on behalf of the company) |

### ContractContact (key fields)

`Id`, `CoworkerFullName`, `Email`, `FullName`, `ContractContactType`

#### ContractContact enum values

| Option | Valid values |
| ------ | ------------ |
| `--contract-contact-type` | `0` None, `1` Director, `2` CompanyAlias, `3` NominatedRecipient |

<!-- END:GENERATED entity=ContractContacts -->
