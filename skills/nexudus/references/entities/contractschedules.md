# ContractSchedules

<!-- BEGIN:GENERATED entity=ContractSchedules -->

A **ContractSchedule** defines a future price change for a plan contract (`CoworkerContract`). On the date specified by `ApplyOn`, the system automatically updates the contract's price to the value in `Price`.

Schedules allow operators to pre-configure stepped pricing — for example, an introductory rate for the first few months that transitions to a full rate on a known date — without any manual intervention at the time of the change.

Once a schedule has been processed, `Applied` is set to `true` and the record becomes read-only.

ContractSchedules support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus contractschedules list --agent` | List all contractschedules |
| `nexudus contractschedules list --id <id> --agent` | Filter by single ID |
| `nexudus contractschedules list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus contractschedules list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus contractschedules list --price <value> --apply-on <value> --agent` | Filter contractschedules by properties |
| `nexudus contractschedules list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus contractschedules get <id> --agent` | Get single contractschedule |
| `nexudus contractschedules create --coworker-contract-id <value> --apply-on <value> --agent` | Create contractschedule |
| `nexudus contractschedules update <id> --name "New Name" --agent` | Update contractschedule |
| `nexudus contractschedules delete <id> --yes --agent` | Delete contractschedule (no prompt) |

#### ContractSchedule list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the coworker contract linked to this record |
| `--notes` | string | Optional notes or internal comments about this scheduled price change |
| `--price` | decimal | The new contract price to apply on the scheduled date |
| `--from-price` | range | |
| `--to-price` | range | |
| `--apply-on` | DateTime | Date on which the system will automatically update the contract price to the value in Price |
| `--from-apply-on` | range | |
| `--to-apply-on` | range | |
| `--apply-on-local` | DateTime | Date/time value for apply on local |
| `--from-apply-on-local` | range | |
| `--to-apply-on-local` | range | |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### ContractSchedule create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long, required | ID of the coworker contract linked to this record |
| `--notes` | string | Optional notes or internal comments about this scheduled price change |
| `--price` | decimal | The new contract price to apply on the scheduled date |
| `--apply-on` | DateTime, required | Date on which the system will automatically update the contract price to the value in Price |
| `--apply-on-local` | DateTime | Date/time value for apply on local |

#### ContractSchedule update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-contract-id` | long | ID of the coworker contract linked to this record |
| `--notes` | string | Optional notes or internal comments about this scheduled price change |
| `--price` | decimal | The new contract price to apply on the scheduled date |
| `--apply-on` | DateTime | Date on which the system will automatically update the contract price to the value in Price |
| `--apply-on-local` | DateTime | Date/time value for apply on local |

#### ContractSchedule PII fields

In non-interactive mode, these fields are tokenized in output. You can pass those tokens back into create/update options and the CLI resolves them before sending API requests.

| Option | Category | Token example |
| --- | --- | --- |
| `--coworker-contract-coworker-full-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--coworker-contract-coworker-billing-name` | `NAME` | `«PII:NAME:a3f2b1c9»` |
| `--notes` | `BIO` | `«PII:BIO:a3f2b1c9»` |

Example:

`nexudus contractschedules update <id> --coworker-contract-coworker-full-name "«PII:NAME:a3f2b1c9»" --agent`

### ContractSchedule (key fields)

`Id`, `CoworkerContractCoworkerFullName`, `Price`, `ApplyOn`, `Applied`

<!-- END:GENERATED entity=ContractSchedules -->
