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
| `nexudus coworkeraccesscontrolaudits get <id> --agent` | Get single coworkeraccesscontrolaudit |
| `nexudus coworkeraccesscontrolaudits create --coworker-id <value> --agent` | Create coworkeraccesscontrolaudit |
| `nexudus coworkeraccesscontrolaudits update <id> --name "New Name" --agent` | Update coworkeraccesscontrolaudit |
| `nexudus coworkeraccesscontrolaudits delete <id> --yes --agent` | Delete coworkeraccesscontrolaudit (no prompt) |

#### CoworkerAccessControlAudit list filter options

`--coworker-id` (long), `--description`, `--is-problem` (bool), `--from-created-on` (range), `--to-created-on` (range), `--from-updated-on` (range), `--to-updated-on` (range)

#### CoworkerAccessControlAudit create options

`--coworker-id` (long, required), `--description`, `--is-problem` (bool)

#### CoworkerAccessControlAudit update options

`--coworker-id` (long), `--description`, `--is-problem` (bool)

<!-- END:GENERATED entity=CoworkerAccessControlAudits -->
