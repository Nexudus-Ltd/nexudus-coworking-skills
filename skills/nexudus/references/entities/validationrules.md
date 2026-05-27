# ValidationRules

<!-- BEGIN:GENERATED entity=ValidationRules -->

A **ValidationRule** defines a custom business rule that validates data before it is saved. Rules can be applied to various record types (coworkers, bookings, contracts, visitors, etc.) and enforce custom conditions beyond the standard field validations.

ValidationRules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus validationrules list --agent` | List all validationrules |
| `nexudus validationrules list --id <id> --agent` | Filter by single ID |
| `nexudus validationrules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus validationrules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus validationrules list --business-id <value> --name <value> --agent` | Filter validationrules by properties |
| `nexudus validationrules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus validationrules get <id> --agent` | Get single validationrule |
| `nexudus validationrules create --business-id <value> --name <value> --record-type <value> --formula <value> --agent` | Create validationrule |
| `nexudus validationrules update <id> --name "New Name" --agent` | Update validationrule |
| `nexudus validationrules delete <id> --yes --agent` | Delete validationrule (no prompt) |

#### ValidationRule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this validation rule |
| `--record-type` | enum | The record type value for this validation rule |
| `--active` | bool | Whether this validation rule is currently active |
| `--formula` | string | The formula value for this validation rule |
| `--description` | string | Free-text description of this validation rule |
| `--error-message` | string | The error message value for this validation rule |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ValidationRule create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the business linked to this record |
| `--name` | string, required | The name value for this validation rule |
| `--record-type` | enum, required | The record type value for this validation rule |
| `--active` | bool | Whether this validation rule is currently active |
| `--formula` | string, required | The formula value for this validation rule |
| `--description` | string | Free-text description of this validation rule |
| `--error-message` | string | The error message value for this validation rule |

#### ValidationRule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the business linked to this record |
| `--name` | string | The name value for this validation rule |
| `--record-type` | enum | The record type value for this validation rule |
| `--active` | bool | Whether this validation rule is currently active |
| `--formula` | string | The formula value for this validation rule |
| `--description` | string | Free-text description of this validation rule |
| `--error-message` | string | The error message value for this validation rule |

#### ValidationRule enum values

| Option | Valid values |
| ------ | ------------ |
| `--record-type` | `1` Coworker, `2` Booking, `4` CoworkerContract, `5` Visitor, `6` CoworkerProduct, `7` ProposalContract, `8` CoworkerInvoice, `9` Teams, `10` EventAttendees |

<!-- END:GENERATED entity=ValidationRules -->
