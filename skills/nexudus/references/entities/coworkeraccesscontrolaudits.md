# CoworkerAccessControlAudits

<!-- BEGIN:GENERATED entity=CoworkerAccessControlAudits -->

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

`--coworker-id`, `--description`, `--is-problem`

#### CoworkerAccessControlAudit create options

`--coworker-id` (required), `--description`, `--is-problem`

#### CoworkerAccessControlAudit update options

`--coworker-id`, `--description`, `--is-problem`

<!-- END:GENERATED entity=CoworkerAccessControlAudits -->
