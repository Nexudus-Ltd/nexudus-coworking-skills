# EloxxLockersAudits

<!-- BEGIN:GENERATED entity=EloxxLockersAudits -->

EloxxLockersAudits support Search, Get, Create, Update, Delete.

| Command | Description |
| --- | --- |
| `nexudus eloxxlockersaudits list --agent` | List all eloxxlockersaudits |
| `nexudus eloxxlockersaudits list --id <id> --agent` | Filter by single ID |
| `nexudus eloxxlockersaudits list --id <id1> --id <id2> --agent` | Filter by multiple IDs |
| `nexudus eloxxlockersaudits list --unique-id <guid> --agent` | Filter by UniqueId (GUID) |
| `nexudus eloxxlockersaudits list --business-id <value> --floor-plan-desk-id <value> --agent` | Filter eloxxlockersaudits by properties |
| `nexudus eloxxlockersaudits list --page-number 2 --page-size 10 --agent` | Paginated list |
| `nexudus eloxxlockersaudits get <id> --agent` | Get single eloxxlockersaudit |
| `nexudus eloxxlockersaudits create --business-id <value> --floor-plan-desk-id <value> --coworker-id <value> --description <value> --agent` | Create eloxxlockersaudit |
| `nexudus eloxxlockersaudits update <id> --name "New Name" --agent` | Update eloxxlockersaudit |
| `nexudus eloxxlockersaudits delete <id> --yes --agent` | Delete eloxxlockersaudit (no prompt) |

#### EloxxLockersAudit list filter options

`--business-id`, `--floor-plan-desk-id`, `--coworker-id`, `--description`, `--action-by`, `--action`, `--tile-audit-type`

#### EloxxLockersAudit create options

`--business-id` (required), `--floor-plan-desk-id` (required), `--coworker-id` (required), `--description` (required), `--action-by`, `--action`, `--tile-audit-type`

#### EloxxLockersAudit update options

`--business-id`, `--floor-plan-desk-id`, `--coworker-id`, `--description`, `--action-by`, `--action`, `--tile-audit-type`

<!-- END:GENERATED entity=EloxxLockersAudits -->
