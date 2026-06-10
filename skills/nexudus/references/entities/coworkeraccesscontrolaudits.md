# CoworkerAccessControlAudits

<!-- BEGIN:GENERATED entity=CoworkerAccessControlAudits -->

A **CoworkerAccessControlAudit** records any issue encountered when connecting to an access control system, granting permissions to a customer, or updating their profile in those systems.

Entries with `IsProblem = true` indicate that the operation failed or produced an error. Use `Description` to understand what went wrong.

CoworkerAccessControlAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus coworkeraccesscontrolaudits list --agent` | List all coworkeraccesscontrolaudits |
| `nexudus coworkeraccesscontrolaudits list --id <id> --agent` | Filter by single ID |
| `nexudus coworkeraccesscontrolaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus coworkeraccesscontrolaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus coworkeraccesscontrolaudits list --coworker-id <value> --description <value> --agent` | Filter coworkeraccesscontrolaudits by properties |
| `nexudus coworkeraccesscontrolaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus coworkeraccesscontrolaudits list --order-by <property> --dir 0 --agent` | Sort results (0=asc, 1=desc) |
| `nexudus coworkeraccesscontrolaudits get <id> --agent` | Get single coworkeraccesscontrolaudit |
| `nexudus coworkeraccesscontrolaudits create --coworker-id <value> --agent` | Create coworkeraccesscontrolaudit |
| `nexudus coworkeraccesscontrolaudits update <id> --name "New Name" --agent` | Update coworkeraccesscontrolaudit |
| `nexudus coworkeraccesscontrolaudits delete <id> --yes --agent` | Delete coworkeraccesscontrolaudit (no prompt) |

#### CoworkerAccessControlAudit list filter options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer affected by the access control operation |
| `--description` | string | Human-readable description of the issue encountered in the access control system |
| `--is-problem` | bool | Whether this entry represents a failed or problematic operation in the access control system |
| `--from-created-on` | range | |
| `--to-created-on` | range | |
| `--from-updated-on` | range | |
| `--to-updated-on` | range | |

#### CoworkerAccessControlAudit sorting

| Option | Description |
| --- | --- |
| `--order-by <property>` | Property name to sort by |
| `--dir <0\|1>` | Sort direction: 0 = ascending, 1 = descending |

Default sort: `Id` ascending. If no `--order-by` is specified, the API returns results ordered by `Id` (ascending).

#### CoworkerAccessControlAudit create options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long, required | ID of the customer affected by the access control operation |
| `--description` | string | Human-readable description of the issue encountered in the access control system |
| `--is-problem` | bool | Whether this entry represents a failed or problematic operation in the access control system |

#### CoworkerAccessControlAudit update options

| Option | Type | Description |
| --- | --- | --- |
| `--coworker-id` | long | ID of the customer affected by the access control operation |
| `--description` | string | Human-readable description of the issue encountered in the access control system |
| `--is-problem` | bool | Whether this entry represents a failed or problematic operation in the access control system |

<!-- END:GENERATED entity=CoworkerAccessControlAudits -->
