# ValidationRules

<!-- BEGIN:GENERATED entity=ValidationRules -->

A validation rule is a location-scoped custom expression evaluated when selected records are created or updated; a false result blocks the save with its configured error message.

ValidationRules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus validationrules list --agent` | List all validationrules |
| `nexudus validationrules list --id <id> --agent` | Filter by single ID |
| `nexudus validationrules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus validationrules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus validationrules list --business-id <value> --name <value> --agent` | Filter validationrules by properties |
| `nexudus validationrules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus validationrules list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus validationrules get <id> --agent` | Get single validationrule |
| `nexudus validationrules create --business-id <value> --name <value> --record-type <value> --formula <value> --agent` | Create validationrule |
| `nexudus validationrules update <id> --name "New Name" --agent` | Update validationrule |
| `nexudus validationrules delete <id> --yes --agent` | Delete validationrule (no prompt) |

#### ValidationRule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this rule; a rule on a network location is also evaluated for records in its child locations |
| `--name` | string | Required internal name for this rule; it is returned as the failure message when ErrorMessage is null |
| `--record-type` | enum | Record type this rule evaluates: Coworker (customer), Booking, CoworkerContract, Visitor, CoworkerProduct, ProposalContract, CoworkerInvoice, Teams, or EventAttendees |
| `--active` | bool | Whether this rule is evaluated when a matching record is created or updated; only active rules are selected for evaluation |
| `--formula` | string | Required Flee expression that returns true to allow the record and false to reject it; use record, isCreate, isUpdate, user, and the available CustomFunctions as evaluation context |
| `--description` | string | Optional internal notes explaining this rule; not shown to customers |
| `--error-message` | string | Message returned when Formula evaluates to false; when null, the rule Name is returned instead |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ValidationRule sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### ValidationRule create options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long, required | ID of the location that owns this rule; a rule on a network location is also evaluated for records in its child locations |
| `--name` | string, required | Required internal name for this rule; it is returned as the failure message when ErrorMessage is null |
| `--record-type` | enum, required | Record type this rule evaluates: Coworker (customer), Booking, CoworkerContract, Visitor, CoworkerProduct, ProposalContract, CoworkerInvoice, Teams, or EventAttendees |
| `--active` | bool | Whether this rule is evaluated when a matching record is created or updated; only active rules are selected for evaluation |
| `--formula` | string, required | Required Flee expression that returns true to allow the record and false to reject it; use record, isCreate, isUpdate, user, and the available CustomFunctions as evaluation context |
| `--description` | string | Optional internal notes explaining this rule; not shown to customers |
| `--error-message` | string | Message returned when Formula evaluates to false; when null, the rule Name is returned instead |

#### ValidationRule update options

| Option | Type | Description |
| --- | --- | --- |
| `--business-id` | long | ID of the location that owns this rule; a rule on a network location is also evaluated for records in its child locations |
| `--name` | string | Required internal name for this rule; it is returned as the failure message when ErrorMessage is null |
| `--record-type` | enum | Record type this rule evaluates: Coworker (customer), Booking, CoworkerContract, Visitor, CoworkerProduct, ProposalContract, CoworkerInvoice, Teams, or EventAttendees |
| `--active` | bool | Whether this rule is evaluated when a matching record is created or updated; only active rules are selected for evaluation |
| `--formula` | string | Required Flee expression that returns true to allow the record and false to reject it; use record, isCreate, isUpdate, user, and the available CustomFunctions as evaluation context |
| `--description` | string | Optional internal notes explaining this rule; not shown to customers |
| `--error-message` | string | Message returned when Formula evaluates to false; when null, the rule Name is returned instead |

#### ValidationRule enum values

| Option | Valid values |
| ------ | ------------ |
| `--record-type` | `1` Coworker, `2` Booking, `4` CoworkerContract, `5` Visitor, `6` CoworkerProduct, `7` ProposalContract, `8` CoworkerInvoice, `9` Teams, `10` EventAttendees |

<!-- END:GENERATED entity=ValidationRules -->
