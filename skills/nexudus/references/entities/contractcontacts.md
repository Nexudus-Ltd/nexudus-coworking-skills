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

`--coworker-contract-id`, `--coworker-id`, `--email`, `--full-name`, `--date-of-birth`, `--from-date-of-birth` (range), `--to-date-of-birth` (range), `--address`, `--post-code`, `--city-name`, `--state`, `--country-id`, `--phone-number`, `--notes`, `--contract-contact-type`, `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### ContractContact create options

`--coworker-contract-id` (required), `--coworker-id`, `--email`, `--full-name` (required), `--date-of-birth`, `--address`, `--post-code`, `--city-name`, `--state`, `--country-id`, `--phone-number`, `--notes`, `--contract-contact-type` (required)

#### ContractContact update options

`--coworker-contract-id`, `--coworker-id`, `--email`, `--full-name`, `--date-of-birth`, `--address`, `--post-code`, `--city-name`, `--state`, `--country-id`, `--phone-number`, `--notes`, `--contract-contact-type`

### ContractContact (key fields)

`Id`, `CoworkerFullName`, `Email`, `FullName`, `ContractContactType`

#### ContractContact enum values

| Option | Valid values |
| ------ | ------------ |
| `--contract-contact-type` | `0` None, `1` Director, `2` CompanyAlias, `3` NominatedRecipient |

<!-- END:GENERATED entity=ContractContacts -->
